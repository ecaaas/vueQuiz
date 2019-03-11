<template>
  <div id="app">
    <img alt="Vue logo" src="./assets/Logo.png">
    <HelloWorld msg="Teater Quiz"/>
    <br><br>
    <router-link to="/kelas">Data Kelas</router-link>
    &nbsp
    <router-link to="/siswa">Data Siswa</router-link>
  </div>
</template>

<script>
import HelloWorld from './components/HelloWorld.vue'


export default {
  name: 'app',
  components:{
    HelloWorld
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
