<template>
  <div>
    <canvas id="myChart"/>
  </div>
</template>

<script>
/* eslint-disable */
// Chart.js 3.0 and upwards is tree shakeable, so we have to import and register elements
// console 창 확인하면 편리함
import {ArcElement, Chart, PolarAreaController, RadialLinearScale} from "chart.js";

export default {
  name: "PolarChart",
  props: ['chartData'],
  mounted() {
    Chart.register(ArcElement, PolarAreaController, RadialLinearScale)
    const config = {
      type: 'polarArea',
      data: this.chartData,
      options: {
        responsive: true,
        scales: {
          r: {
            pointLabels: {
              display: true,
              centerPointLabels: true,
              font: {
                size: 18
              }
            }
          }
        },
        plugins: {
          legend: {
            position: 'top',
          },
          title: {
            display: true,
            text: 'Chart.js Polar Area Chart With Centered Point Labels'
          }
        }
      },
    }
    new Chart(document.getElementById('myChart'), config)
  }
  ,
}
</script>

<style scoped>

</style>
