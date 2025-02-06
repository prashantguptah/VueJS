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

    <input :checked="isRed" v-model="isRed" type="checkbox" @click="red"/> Red
   
    

    




    <div :style="{color:colored}">
      <h1>Hello {{ input }}</h1>
    </div>


    <!--                 OR                -->


      <!-- <div v-bind:style="{color: color_value.color}">
        <h1>Hello {{ input }}</h1>
    </div> -->

    <select  v-model="colored">
      <option disabled value="">Select the color</option>
      <option value="red">red</option>
      <option value="blue">blue</option>
      <option value="green">green</option>
      <option value="black">black</option>
      <option v-for="(col,index) in colors" :key="index">{{ col }}</option>
    </select>


    <!--             OR            -->


    <!-- <select v-model="color_value">
            <option v-bind:value="{color: 'red'}">red</option>
            <option v-bind:value="{color: 'yellow'}">yellow</option>
            <option v-bind:value="{color: 'black'}">black</option>
            <option v-bind:value="{color: 'orange'}">orange</option>
            <option v-for="(col, index) in colors" v-bind:key="index" v-bind:value="{color: col}">{{col}}</option>
        </select> -->
    <hr>


   
  </div>
</template>




<script>
export default {
  name: "TestComponent",
  data() {
    return {
      input:"Prashant",
      date : false,
      isRed: false,
      colored:"",
      colors: ["red","yellow", "black", "orange"]
      // color_value: {
      //     color: "black"
      // },
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