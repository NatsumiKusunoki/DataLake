<template>
  <div class="hello">
    <barChart></barChart>
    <lineChart></lineChart>
    <pieChart></pieChart>
  </div>
</template>

<script>
import barChart from './barCharts.vue'
import lineChart from './lineCharts.vue'
import pieChart from './pieCharts.vue'

export default {
  name: 'HelloWorld',
  data () {
    return {
      // msg: 'Welcome to Your Vue.js App'
    }
  },
  components: {
    barChart,
    lineChart,
    pieChart
  },
  methods: {

  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h1, h2 {
  font-weight: normal;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
.barCharts,.lineCharts,.pieCharts{
  width: 40%;
  float: left;
  margin: 2% 0;
}
</style>
