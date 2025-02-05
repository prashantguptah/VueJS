
<!-- option API -->
<!-- 
<script>
export default{

  data(){
    return {
      count: 0
    }
  },


  methods:{
    increment(){
      this.count++
    }
  },


  mounted(){
    console.log(`The initial count is ${this.count}`)
  }
}
</script>


<template>
  <button @click="increment">Count is: {{ count }}</button>
</template> -->


<!-- composition API -->

<!-- 
<script setup>
import {ref,onMounted} from "vue"

const count = ref(0)

function increment(){
  count.value++
}

onMounted(()=>{
  console.log(`The initial count is ${count.value}.`)
})
</script>


<template>
  <button @click="increment">Count is: {{ count }}</button>

  <span style="color: red">This should be red.</span>

  
</template> -->





<!-- v-html directive -->

<!-- <template>
  <div v-html="rawHtml"></div>
</template>

<script>
export default {
  data() {
    return {
      rawHtml: "<p style='color: red;'>This is a red paragraph.</p>"
    };
  }
};
</script> -->





<!-- v-bind -->


<!-- <script setup>
   const objectOfAttrs = {
  id: 'container',
  class: 'wrapper',
  style: 'background-color:green'
}
</script>

 <template>
      <div v-bind="objectOfAttrs">my name is pp</div>

      
</template> -->



