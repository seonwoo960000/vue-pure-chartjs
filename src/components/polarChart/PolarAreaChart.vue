<template>
  <div>
    <canvas :id="id"/>
  </div>
</template>

<script>
import {ArcElement, Chart, PolarAreaController, RadialLinearScale} from "chart.js";

export default {
  name: "PolarChart",
  props: ['chartData'],
  mounted() {
    this.initializeChart()
  },
  watch: {
    chartData() {
      this.initializeChart()
    }
  },
  computed: {
    id() {
      return `polar-area-chart-${this._uid}`
    }
  },
  data: () => ({
    myChart: null
  }),
  methods: {
    initializeChart() {
      if (!this.chartData) return
      Chart.register(ArcElement, PolarAreaController, RadialLinearScale)
      const config = {
        type: 'polarArea',
        data: this.chartData,
        options: {
          responsive: true,
          scales: {
            r: {
              min: 0,
              max: 5,
              ticks: {
                stepSize: 1,
              },
              pointLabels: {
                display: true,
                centerPointLabels: true,
                font: {
                  size: 12,
                  family: "'Noto Sans KR', 'sans-serif'",
                  weight: 600
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
      this.myChart = new Chart(document.getElementById(this.id), config)
    }
  },
  beforeDestroy() {
    if (this.myChart) this.myChart.destroy()
  }
}
</script>

<style scoped>

</style>
