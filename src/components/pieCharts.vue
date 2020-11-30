<template>
  <div class="pieCharts">
    <div id="pieCharts" class="myPie"></div>
  </div>
</template>

<script>
  import echarts from 'echarts'

  export default{
    name: 'pieCharts',
    methods: {
      myPieCharts() {
        var mychart = this.$echarts.init(document.getElementById("pieCharts"));

        var pieData = [{
          name: 'Mon',
          value:1012
        },{
          name: 'Tue',
          value:1090
        },{
          name: 'Wed',
          value:1145
        },{
          name: 'Thur',
          value:1198
        },{
          name: 'Fri',
          value:1387
        },{
          name: 'Sat',
          value:1411
        },{
          name: 'Sun',
          value:1261
        }
        ]

        var option = {
          title: {
            text: '饼图'
          },
          tooltip: {
            
          },
          legend: {
            data: ['销量']
          },
          series: [{
            name:'销量',
            type: 'pie',
            data: pieData,
            label:{
              show:true,
              formatter:function(arg){
                console.log(arg);
                return arg.name + ': ' + arg.percent + '%';
              }
            },
            roseType:'radius',   //南丁格尔图
            selectedMode: 'multiple',
            selectedOffset:30
          }]
        }
        mychart.setOption(option)
      }
    },
    mounted() {
      this.myPieCharts()
    }
  }
</script>

<style>
  .myPie{
    width: 600px;
    height: 400px;
  }
</style>
