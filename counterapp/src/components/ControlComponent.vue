<template>
    <div class="controls">
      <button v-on:click="startTimer">Start</button>
      <button v-on:click="stopTimer">Stop</button>
    </div>
  </template>
  
  <script>
  export default {
    props: ['startCountdown', 'stopCountdown'],
    methods: {
      startTimer() {
        this.startCountdown();
      },
      stopTimer() {
        this.stopCountdown();
      },
    },
  };
  </script>
  
  <style scoped>
  .controls {
    text-align: center;
    margin-top: 20px;
  }
  button {
    padding: 10px 20px;
    margin: 5px;
    font-size: 1rem;
    border: none;
    border-radius: 5px;
  }
  button:first-child {
    background-color: green;
    color: white;
  }
  button:last-child {
    background-color: red;
    color: white;
  }
  </style>
  