<template>

  <div>



    <div :class="{red:isRed}">
      <h1>Hello {{ input }}</h1>
    </div>
   
    <input type="text" v-model="input">
    {{ date }}

    <br>
    <button v-on:click="clear">Clear</button>
    <button v-on:click="capitals">Capital</button>

    <hr>
    

    <input :checked="isRed" v-model="isRed" type="checkbox" @click="red"/> Red


   
  </div>
</template>




<script>
export default {
  name: "TestComponent",
  data() {
    return {
      input:"Prashant",
      date : false,
      isRed: false
    };
  },

  created: function(){
    this.date = new Date().getFullYear() + "-" + new Date().getMonth() + "-" + new Date().getDay()
  },
  mounted: function(){
    
    this.date = new Date().getFullYear() + "-" + new Date().getMonth() + "-" + new Date().getDay()
  },

  methods:{
    clear: function(){
        this.input = ""
    },
    capitals: function(){
     this.input = this.input.toUpperCase()
    },
    red: function(){
      console.log(this.isRed)
    }
    
    
  }
};
</script>



<style>

.red{
  color: red;
}

.green{
  color: green;
}

</style>