<template>


<div :style="styleObject">Hello Vue</div>



<!-- form input bindings -->
 

<!-- input text -->
<p>message is: {{ message }}</p>
<input type="text" placeholder="Enter the data" v-model="message">


<!-- multiline  text-->


 <p>Multiline Text {{ multimessage }}</p>
 <textarea placeholder="Enter inputs" v-model="multimessage"></textarea>



 <!-- checkbox -->


  <input type="checkbox" id="checkbox" v-model="checked">
  <label for="checkbox">{{ checked }}</label>



  <!-- multiple checkbox -->


  <div>Checked names: {{ checkedNames }}</div>

  <input type="checkbox" id="Jack" value="Jack" v-model="checkedNames">
  <label for="Jack">Jack</label>
  <input type="checkbox" id="Sam" value="Sam" v-model="checkedNames">
  <label for="Sam">Sam</label>
  <input type="checkbox" id="Sunil" value="Sunil" v-model="checkedNames">
  <label for="Sunil">Sunil</label>
  <input type="checkbox" id="Ravi" value="Ravi" v-model="checkedNames">
  <label for="Ravi">Ravi</label>




  <!-- select option -->


  <div>Selected: {{ selected }}</div>

  <select  v-model="selected">
    <option disabled value="">Please select one</option>
    <option value="A">A</option>
    <option value="B">B</option>
    <option value="C">C</option>
  </select>
   
</template>







<script>

export default{
    name: "PracticeComponent",
    data(){
        return {
            message:"",
            multimessage:"",
            checked:true,
            checkedNames:[],
            selected:"",
            styleObject:{
                color: "blue",
                fontsize: 20
            }
        }
    },
    
}


</script>