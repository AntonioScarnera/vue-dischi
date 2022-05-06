<template>
    <section class="container">
        <loader-comp v-if="loading" />
        <div class="row gap-3 d-flex justify-content-center">
            <div v-for="disc in  discList" :key="disc.id" class="col-lg-2 col-md-6">
                <card-comp :item="disc" />
            </div>
        </div>
    </section>

</template>

<script>
import LoaderComp from './LoaderComp.vue'
import CardComp from './CardComp.vue'
import axios from 'axios'

export default {
    name: 'GridComp',
    components:{
        CardComp,
        LoaderComp
        
    },
    data(){
        return{
            discList: [],
            apiPath: 'https://flynn.boolean.careers/exercises/api/array/',
            loading: false
        }
    },
    mounted(){
        this.loading = true;
        axios.get(this.apiPath + 'music').then((res)=>{
            this.discList = res.data.response;
            console.log(this.discList);
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