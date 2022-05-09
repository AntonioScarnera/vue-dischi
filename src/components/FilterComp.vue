<template>
    <div>
        <form>
            <select name="genre" id="genre" v-model="selectGenre" @change="searchGenre">
                <option value="">all</option>
                <option :value="genere" v-for="(genere, index) in discType" :key="index">{{genere}}</option>
            </select>
            <select name="author" id="author" v-model="selectAuthor" @change="search">
                <option value="">all</option>
                <option :value="autore" v-for="(autore, index) in discType" :key="index">{{autore}}</option>
            </select>
        </form>
    </div>
</template>

<script>
export default {
    name: 'FilterComp',
    data(){
        return{
            selectGenre: '',
            selectAuthor: ''
        }
    },
    methods:{
        searchGenre(){
            this.$emit('mysearch',this.selectGenre)
            //this.inputText = ''
        }
    },
    props:['discType']
}
</script>

<style>

</style>