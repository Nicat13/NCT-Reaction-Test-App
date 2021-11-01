<template>
  <h1>MyPomodoro</h1>
  <select v-model="selectedStep">
    <option value="0">Pomodoro</option>
    <option value="1">Short Break</option>
    <option value="2">Long Break</option>
  </select>
  <p>{{ curretnStatusText }}</p>
  <p>{{ statusTextChanger }}</p>
</template>

<script>
export default {
  data() {
    return {
      selectedStep: 0,
      curretnStatusText: "Time to focus!",
    };
  },
  computed: {
    statusTextChanger() {
      return this.selectedStep != 0 ? "Time for a break!" : "Time to focus!";
    },
  },
};
</script>

<style>
</style>