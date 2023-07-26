<template>
    <div class="riga">
        <div class="value"> {{riga}} </div>
        <div class="delete" v-if="!isHeader" @click="eliminaRiga"> X </div>
    </div>
</template>

<script>
export default{
    props:['riga','type','index'],
    methods:{
        eliminaRiga(){
            console.log('lo passo a Tabella l\'indice:',this.index);
            this.$emit('eliminaRiga',this.index);
        }
    },
    computed:{
        isHeader(){
            return this.type=='header';
        }
    }
}
</script>

<style scoped>
.riga{
    display: flex;
    margin: 10px;
    border-bottom: solid 1px lightgray;
    .delete{
        margin-left: auto;
        margin-right: 20px;
        cursor: pointer;
    }
}
</style>