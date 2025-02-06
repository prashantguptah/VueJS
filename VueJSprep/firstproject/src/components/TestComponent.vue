<template>

  <div>
    <h1>Hello {{ input }}</h1>
    <input type="text" v-model="input">
    {{ date }}

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
      input:"Prashant",
      date : false
    };
  },

  created: function(){
    console.log("Created "+ this.input)
    this.date = new Date()
  },
  mounted: function(){
    console.log("mounted"+ this.date)
    this.date = new Date()
  },
  updated: function(){
    console.log("updated" +this.date)
    // this.date = new Date()   error =  Maximum recursive updates
  },
  unmounted: function(){
    console.log("destroyed" + this.date)
    this.date = new Date()
  },

  methods:{
    clear: function(){
        this.input = ""
    },
    capitals: function(){
     this.input = this.input.toUpperCase()
    },
    
    // computed: {
    //     date: {
    //         set: function(newvalue) {
    //             console.log(newvalue);
    //             this.date = new Date(newvalue).getTime();
    //         }
    //     }
    // },
  }
};
</script>



<style>

</style>