<template>
<div id="app">
<img src="./assets/logo.png">
<test/>
<Home/>
</div>
</template>

<script>

import Test from './components/Test.vue';
import Home from './components/Home.vue';
export default {
  name: 'app',
  components: {
    Test,
    Home
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
  margin-top: 60px;
}
</style>
