<template>
  <div>
    <ChartVue />
  </div>
</template>

<script>
import ChartVue from './components/Chart.vue';
export default {
  name: 'App',
  components: {
    ChartVue,
  }
}
</script>

<style>
#app {
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
