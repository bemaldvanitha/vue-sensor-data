<template>
  <div id="app" class="container">

    <div class="row mt-5" v-if="sensorData.length > 0" >
      <div class="col">

        <h2>{{ chatTitle }}</h2>
        <line-chart :chartData="sensorData" :options="chartOptions" :label="chatTitle"></line-chart>
      </div>

    </div>

  </div>
</template>

<script>
import axios from 'axios';
import moment from 'moment';
import LineChart from '../components/LineChart'

export default {
  name: 'SensorCharts',
  components: {
    LineChart
  },
  data(){
    return {
      chartOptions: {
        responsive: true,
        maintainAspectRatio: false
      },
      sensorData: [],
      chatTitle: 'Temperature * c'
    };
  },
  created()  {
    axios.get(`http://localhost:5000/sensorData`).then(response => {
      const data = response.data;

      data.forEach(singleData => {
        const date = moment(singleData.date,"YYYYMMDD").format("MM/DD");
        const value = singleData.data_value;

        this.sensorData.push({
          date: date,
          value: value
        });
      })
    });
  }
}
</script>

<style>

</style>
