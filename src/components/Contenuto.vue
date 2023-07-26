<template>
    <div class="contenitore">
        <div class="input">
            <input type="text" v-model="stringaDaAggiungere" placeholder="Stringa da Aggiungere">
            <button @click="aggiungiStringa"> Aggiungi </button>
        </div>
        <div class="tabelle-container">
            <Tabella :tabella="vettoreStringhe" @eliminaRiga="eliminaRiga"/>
            <Tabella :tabella="vettoreStringheMaiuscolo" @eliminaRiga="eliminaRiga"/>
        </div>
    </div>
</template>

<script>
import Tabella from './Tabella.vue';

export default{
    data(){
        return {
            stringaDaAggiungere:"",
            vettoreStringhe:[]
        }
    },
    methods:{
        aggiungiStringa(){
            this.vettoreStringhe.push(this.stringaDaAggiungere)
        },
        eliminaRiga(index){
            this.vettoreStringhe.splice(index,1);
        }
    },
    computed:{
        vettoreStringheMaiuscolo(){
            return this.vettoreStringhe.map(item=>item.toUpperCase())
        }
    },
    components:{ Tabella }
}

</script>

<style scoped lang="scss">
@import "../assets/variables.scss";

.contenitore{
    width: 100vw;
    height: calc(100vh - 2*$base-height);
    .tabelle-container{
        display: flex;
    }
}
</style>