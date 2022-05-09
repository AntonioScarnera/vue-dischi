<template>
    <div>
        <form>
            <select name="genre" id="genre" v-model="selectGenre" @change="search">
                <option value="">all</option>
                <option :value="genere" v-for="(genere, index) in discType" :key="index">{{genere}}</option>
            </select>
        </form>
    </div>
</template>

<script>
export default {
    name: 'FilterComp',
    data(){
        return{
            selectGenre: ''
        }
    },
    methods:{
        search(){
            this.$emit('mysearch',this.selectGenre)
            //this.inputText = ''
        }
    },
    props:['discType']
}
</script>

<style>

</style>