<template>
<div id="app">
<img src="./assets/logo.png">
<test/>
<Home/>
<Methods/>
<Events/>
<Two_way/>
</div>
</template>

<script>

import Test from './components/Test.vue';
import Home from './components/Home.vue';
import Methods from './components/Methods.vue';
import Events from './components/Events.vue';
import Two_way from './components/Two_way.vue';

export default {
  name: 'app',
  components: {
    Test,
    Home,
    Methods,
    Events,
    Two_way
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
