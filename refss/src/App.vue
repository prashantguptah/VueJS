<script setup>
import {ref} from "vue"

const count = ref(0)

function  increment(){
  count.value++
}



</script>


<template>
  <button @click= "increment">
  click
  </button>
  {{ count }}

</template>