<template>
  <!--<img alt="Vue logo" src="./assets/logo.png"> -->
  <!--<HelloWorld msg="Welcome to Your Vue.js App"/>-->
  <Header></Header>
  <Principal></Principal>
  <Personas></Personas>
  <Footer></Footer>
</template>

<script>
import HelloWorld from './components/HelloWorld.vue'

import Header from './components/Header.vue'
import Principal from './components/Principal.vue'
import Personas from './components/Personas.vue'
import Footer from './components/Footer.vue'

export default {
  name: 'App',
  components: {
    HelloWorld,

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
