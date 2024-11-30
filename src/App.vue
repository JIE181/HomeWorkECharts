<template>
  <div id="app">
    <SalesChart></SalesChart>
  </div>
</template>

<script>
import SalesChart from './components/SalesChart.vue';

export default {
  name: 'App',
  components: {
    SalesChart
  }
};
</script>

<style>
/* 可以在这里添加一些全局样式，如果需要的话 */
</style>