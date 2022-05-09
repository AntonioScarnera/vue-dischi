<template>
    <section class="container">
        
        <filter-comp @mysearch="setSearchGenreDisc($event)" :discType="genere"/>

        <loader-comp v-if="loading" />

        <div class="row gap-3 d-flex justify-content-center">
            <div v-for="disc in  filteredDisc" :key="disc.id" class="col-lg-2 col-md-4">
                <card-comp :item="disc" />
            </div>
        </div>
    </section>

</template>

<script>
import LoaderComp from './LoaderComp.vue'
import CardComp from './CardComp.vue'
import axios from 'axios'
import FilterComp from './FilterComp.vue'

export default {
    name: 'GridComp',
    components:{
        CardComp,
        LoaderComp,
        FilterComp
        
    },
    data(){
        return{
            discList: [],
            apiPath: 'https://flynn.boolean.careers/exercises/api/array/',
            loading: false,

            genere: [],
            searchGenere: '',

            autore: [],
            searchAuthor: ''
        }
    },
    methods:{
        setSearchGenreDisc(text){
            this.searchGenere = text;
        }
    },
    computed: {
        filteredDisc(){
            if(this.searchGenere === '') return this.discList;
    
            return this.discList.filter((el)=> el.genre === this.searchGenere)
        }
    },
    created(){
        this.loading = true;
        axios.get(this.apiPath + 'music').then((res)=>{
            this.discList = res.data.response;
            
            this.discList.forEach((el)=>{
                if(!this.genere.includes(el.genre)){
                    this.genere.push(el.genre);
                }
            })

            console.log(this.genere)
            console.log(this.filteredDisc);

            this.loading = false;
        }).catch((error)=>{
            console.log(error);
            this.loading = false;
        })
    }
}
</script>

<style lang="scss">
</style>