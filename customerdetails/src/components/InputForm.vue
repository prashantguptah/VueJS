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
       <li v-for="(item, index) in data" :key="index">
         <div class="customerList">
          <span>{{ item.fname }} </span>
          <span>{{ item.lname }} </span>
          <span>{{ item.address }}</span>
         </div>
         <button>Delete</button>
         <input type="checkbox"  >
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
      data: []
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
      }
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
button {
  margin-top: 10px;
  cursor: pointer;
}
.details{
  margin-top: 15px;
}
 .customerList{
 display: grid;
 grid-template-columns: repeat(3,1fr);
 align-items: center;
 }
 .customerList span{
  border: 1px solid black;
  padding: 5px 10px;
 }

</style>
