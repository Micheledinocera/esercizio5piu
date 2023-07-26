<template>
    <Header />
    <Contenuto />
    <Footer />
</template>

<script>
import Header from './components/Header.vue';
import Contenuto from './components/Contenuto.vue';
import Footer from './components/Footer.vue';

export default{
  components:{ Header, Contenuto, Footer}  
}
</script>

<style>
  body{ margin: 0; }
</style>