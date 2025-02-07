<template>
    <div class="timer">
      <h1>{{ time }}</h1>
    </div>
  </template>
  
  <script>
  export default {
    props: {
      time: Number, 
    },
  };
  </script>
  
  <style scoped>
  .timer {
    font-size: 3rem;
    text-align: center;
  }
  </style>
  