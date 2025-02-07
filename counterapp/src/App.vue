
<template>
  <div>
    <TimerComponent :time="timer" />
    <ControlComponent :startCountdown="startCountdown" :stopCountdown="stopCountdown" />
  </div>
</template>

<script>
import TimerComponent from "./components/TimerComponent.vue";
import ControlComponent from "./components/ControlComponent.vue";

export default {
  name: "App",
  components: {
    TimerComponent,
    ControlComponent,
  },
  data() {
    return {
      timer: 0,
      intervalId: null,
    };
  },
  methods: {
    startCountdown() {
      if (!this.intervalId) {
        this.intervalId = setInterval(() => {
          this.timer++;
        }, 1000);
      }
    },
    stopCountdown() {
      clearInterval(this.intervalId);
      this.intervalId = null;
    },
  },
};
</script>

<style>
body {
  
  text-align: center;
  margin-top: 50px;
}
</style>

