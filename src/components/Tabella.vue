<template>
    <div class="tabella">
        <Riga riga="Valore" type="header" />
        <Riga :riga="item" :index="index" type="value" v-for="(item,index) in tabella" :key="item+index" @eliminaRiga="eliminaRiga"/>
    </div>
</template>

<script>
import Riga from './Riga.vue'
export default{
    props:['tabella'],
    methods:{
        eliminaRiga(index){
            console.log('lo passo a Contenuto l\'indice:',index);
            this.$emit('eliminaRiga',index);
        }
    },
    components:{ Riga }
}
</script>

<style scoped>
.tabella{
    width: calc(50vw - 80px);
    margin: 40px auto;
    border: solid 1px lightgray;
    border-radius: 8px;
}

</style>