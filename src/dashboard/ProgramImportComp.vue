<template>
  <CardBig name="Program Imports">

    <template #left-content>
      <canvas ref="chartRef" id="import-chart"></canvas>

    </template>

  </CardBig>

</template>

<script lang="ts" setup>
import CardBig from '@/components/CardBig.vue';

import { Chart } from 'chart.js/auto';
import { ref, onMounted, nextTick } from 'vue'

let ctx

const chartRef = ref(null)


const createChart = async () => {
  const xValues = [50, 60, 70, 80, 90, 100, 110, 120, 130, 140, 150];
  const yValues = [7, 8, 8, 9, 9, 9, 10, 11, 14, 14, 15];

  ctx = document.getElementById('import-chart') as HTMLCanvasElement;
  new Chart(ctx, {
    type: "line",
    data: {
      labels: xValues,
      datasets: [{
        data: [860, 1140, 1060, 1060, 1070, 1110, 1330, 2210, 7830, 2478],
        borderColor: "#ea4141",
        fill: false
      }, {
        data: [1600, 1700, 1700, 1900, 2000, 2700, 4000, 5000, 6000, 7000],
        borderColor: "#41ea7c",
        fill: false
      }, {
        data: [300, 700, 2000, 5000, 6000, 4000, 2000, 1000, 200, 100],
        borderColor: "#4193ea",
        fill: false
      }]
    },
    options: {
      plugins: {
        title: {
          display: true,
          text: 'Import Loans'
        },
        legend: {
          display: false
        }
      }
    }

  });
}
onMounted(async () => {
  await nextTick(async () => {
    if (chartRef.value) {
      await createChart()
    }
  })
})


</script>

<style lang="scss">
#import-chart {
  width: 100% !important;
  height: 100% !important;
}
</style>
