<template>
  <div id="app">
    <h1>{{message}}</h1>
    <!-- <img src="./assets/logo.png"> -->
    <router-view></router-view>
    <test></test>

  </div>
</template>

<script>
import test from './components/Test.vue'
export default {
  name:'app',
  components: {
      test
    },
  data(){
    return {
      message:"learning  vue"
    }
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  /*text-align: center;*/
  color: #2c3e50;
  /*margin-top: 60px;*/
}
</style>
