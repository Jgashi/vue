<template>
  <div id="app">
    <!-- <img alt="Vue logo" src="./assets/logo.png"> -->
    <!-- <HelloWorld msg="Welcome to Your Vue.js App"/> -->
    <!-- <first></first> -->
    <!-- <second></second> -->
    <div class="page page-home">
      <infoBoard :json="this.json" />
    </div>
  </div>
</template>

<script>
import infoBoard from './components/board/articleBoard'
// import first from './components/first.vue' 
// import second from './components/second.vue' 
// import HelloWorld from './components/HelloWorld.vue'

export default {
  name: 'App',
  components: {
    // HelloWorld
    // second
    infoBoard
  },
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
