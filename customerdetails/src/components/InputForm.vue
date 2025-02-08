<template>
  <div class="customerData">
    <h1>Customer Details</h1>

    <form v-on:submit.prevent="submit">
      <label for="fname">First Name</label>
      <input id="fname" type="text" v-model="fname" placeholder="Enter First Name">

      <label for="lname">Last Name</label>
      <input id="lname" type="text" v-model="lname" placeholder="Enter Last Name">

      <label for="address">Address</label>
      <input id="address" type="text" v-model="address" placeholder="Enter Your Address">
      
      <button type="submit">Add</button>
    </form>

    <ol v-bind:style="{ listStyle: 'none' }" class="details">
       <li v-for="(item, index) in data" :key="index" >
         <div class="customerList" :class="{'red': isRed}">
          <p>{{ item.fname }} </p>
          <p>{{ item.lname }} </p>
          <p>{{ item.address }}</p>
          <div>
            <button v-on:click="deleteItem(index)">Delete</button> 
            <input :checked="isRed" v-model="isRed" type="checkbox" @click="red"/>
          </div>
         
         </div>
         
         
       </li>
    </ol>
  </div>
</template>

<script>
export default {
  name: 'InputForm',
  data() {
    return {
      fname: "",
      lname: "",
      address: "",
      data: [],
      isRed: false
    };
  },

  methods: {
    submit() {
      if (this.fname.trim() && this.lname.trim() && this.address.trim()) {
        this.data.push({
          fname: this.fname,
          lname: this.lname,
          address: this.address
        });

        
        this.fname = "";
        this.lname = "";
        this.address = "";
        console.log(data)
      }
    },
    deleteItem(index) {
      this.data.splice(index, 1);
    },
    red() {
  this.isRed = !this.isRed;
}

  }
};



</script>

<style scoped>

*{
  box-sizing: border-box;
  margin: 0;
  padding: 0;
}

.details{
  margin-top: 20px;
}
 .customerList{
 display: grid;
 grid-template-columns: repeat(4,1fr);
 align-items: center;
 background: yellow;
 }
 p{
  border: 1px solid black;
  padding: 5px 10px;
 }
 .customerList div{
  border: 1px solid black;
 

 }
 h1{
  margin-bottom: 20px;
 }
 .red {
  background: red;
  color: white;
}
input{
  padding: 5px;
  margin-right: 20px;
  margin-left: 5px;
}
button{
  height: 25px;
  padding: 6px 10px;
}




</style>
