<template>

  <div>
    <h1>Hello {{ input }}</h1>
    <input type="text" v-model="input">

    <br>
    <button v-on:click="clear">Clear</button>
    <button v-on:click="capitals">Capital</button>
  </div>
</template>




<script>
export default {
  name: "TestComponent",
  data() {
    return {
      input:""
    };
  },
  methods:{
    clear: function(){
        this.input = ""
    },
    capitals: function(){
     this.input = this.input.toUpperCase()
    }
  }
};
</script>



<style>

</style>