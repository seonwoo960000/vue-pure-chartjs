<template>
  <div>
    <polar-area-chart-wrapper/>
  </div>
</template>

<script>

import PolarAreaChartWrapper from "@/components/polarChart/PolarAreaChartWrapper";

export default {
  name: 'App',
  components: {
    'polar-area-chart-wrapper': PolarAreaChartWrapper
  }
}
</script>

<style>

</style>
