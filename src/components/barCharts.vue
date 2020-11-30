<template>
  <div class="barCharts">
    <div id="barCharts" class="myBar"></div>
  </div>
</template>

<script>
  import echarts from 'echarts'

  export default{
    name:  'barCharts',
    methods: {
      myBarCharts() {
        var mychart = this.$echarts.init(document.getElementById("barCharts"));

        var xDataArr=['Mon','Tue','Wed','Thur','Fri','Sat','Sun'];
        var yDataArr=[1012,1090,1145,1198,1387,1411,1261];

        var option = {
          title: {
            text: '柱状图'
          },
          tooltip: {
            trigger: 'axis'
          },
          legend: {
            data: ['销量']
          },
          xAxis: {
            type: 'category',
            data: xDataArr
          },
          yAxis: {
            type: 'value'
          },
          series: [{
            name:'销量',
            type: 'bar',
            data: yDataArr,
            markLine: {
              data: [{
                type: 'average'
              }]
            }
          }]
        }
        mychart.setOption(option)
      }
    },
    mounted() {
      this.myBarCharts()
    }
  }
</script>

<style>
  .myBar{
    width: 600px;
    height: 400px;
  }
</style>
