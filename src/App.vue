<template>
  <Header></Header>
  <Principal></Principal>
  <Personas></Personas>
  <Footer></Footer>
</template>

<script>

import Header from './components/Header.vue'
import Principal from './components/Principal.vue'
import Personas from './components/Personas.vue'
import Footer from './components/Footer.vue'

export default {
  name: 'App',
  components: {
    Header,
    Principal,
    Personas,
    Footer
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 0px;
}
</style>
