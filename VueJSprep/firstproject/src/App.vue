<template>
  <img alt="Vue logo" src="./assets/logo.png">
   <TestComponent/>
   <PracticeComponent/>
</template>

<script>

import TestComponent from "./components/TestComponent.vue";
import PracticeComponent from "./components/PracticeComponent.vue";


export default {
  name: 'App',
  components: {
   
    TestComponent,
    PracticeComponent
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
