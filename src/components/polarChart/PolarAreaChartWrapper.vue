<template>
  <div>
        <polar-area-chart
          :chart-data="chartData"
        />
  </div>
</template>

<script>
/* eslint-disable */
import PolarAreaChart from "@/components/polarChart/PolarAreaChart";

export default {
  name: "PolarWrapper",
  components: {
    'polar-area-chart': PolarAreaChart
  },
  data: () => ({
    chartData: {
      labels: ['Red', 'Orange', 'Yellow', 'Green', 'Blue'],
      datasets: [
        {
          label: 'Dataset 1',
          data: [12, 19, 3, 5, 2, 3],
          backgroundColor: [
            'rgba(255, 99, 132, 0.2)',
            'rgba(54, 162, 235, 0.2)',
            'rgba(255, 206, 86, 0.2)',
            'rgba(75, 192, 192, 0.2)',
            'rgba(153, 102, 255, 0.2)',
            'rgba(255, 159, 64, 0.2)'
          ]
        }
      ]
    },
  })
}
</script>

<style scoped>

</style>
