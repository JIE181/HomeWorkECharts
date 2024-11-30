<template>
    <div ref="chartContainer" style="width: 100%; height: 400px;"></div>
  </template>
  
  <script>
  import * as echarts from 'echarts';
  
  export default {
    name: 'SalesChart',
    mounted() {
      this.initChart();
    },
    methods: {
      initChart() {
        // 基于准备好的dom，初始化echarts实例
        const chart = echarts.init(this.$refs.chartContainer);
  
        // 模拟的电商销售数据（这里以每月销售额为例）
        const salesData = {
          months: ['January', 'February', 'March', 'April', 'May', 'June', 'July', 'August', 'September', 'October', 'November', 'December'],
          salesAmounts: [5000, 6000, 8000, 7000, 9000, 10000, 12000, 11000, 13000, 14000, 15000, 16000]
        };
  
        // 配置项
        const option = {
          title: {
            text: 'Monthly E-commerce Sales',
            left: 'center'
          },
          tooltip: {
            trigger: 'axis'
          },
          xAxis: {
            type: 'category',
            data: salesData.months
          },
          yAxis: {
            type: 'value'
          },
          series: [
            {
              name: 'Sales Amount',
              type: 'bar',
              data: salesData.salesAmounts
            }
          ]
        };
  
        // 使用刚指定的配置项和数据显示图表。
        chart.setOption(option);
      }
    }
  };
  </script>