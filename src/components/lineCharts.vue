<template>
  <div class="lineCharts">
    <div id="lineCharts" class="myLine"></div>
  </div>
</template>

<script>
  import echarts from 'echarts'

  export default{
    name: 'lineCharts',
    methods: {
      myLineCharts() {
        var mychart = this.$echarts.init(document.getElementById("lineCharts"));

        var xDataArr=['Mon','Tue','Wed','Thur','Fri','Sat','Sun'];
        var yDataArr=[1012,1090,1145,1198,1387,1411,1261];

        var option = {
          title: {
            text: '折线图'
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
            type: 'line',
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
      this.myLineCharts()
    }
  }
</script>

<style>
  .myLine{
    width: 600px;
    height: 400px;
  }
</style>
