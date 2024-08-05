<template>
  <CardBig name="Revenue">
    <template #head-content>

    </template>
    <template #left-content>
      <div id="data" class="column gap-10 fit">
        <CardSmall name="Total Income" value="$3.8M" subvalue="3.1M previous" percentage="+23.2" />
        <CardSmall name="Transactions" value="345" subvalue="2298 previous" percentage="+12.8" />
        <CardSmall name="Expenses" value="$1.4M" subvalue="$1.7M previous" percentage="-4.54" />
      </div>
    </template>

    <template #right-content>
      <canvas ref="chartRef" id="Revenue-chart"></canvas>
    </template>
  </CardBig>
</template>

<script lang="ts" setup>
import CardSmall from '@/components/CardSmall.vue';
import CardBig from '@/components/CardBig.vue';
import { Chart } from 'chart.js/auto';
import { ref, onMounted, nextTick } from 'vue'

let ctx

const chartRef = ref(null)


const createChart = async () => {
  const xValues = [50, 60, 70, 80, 90, 100, 110, 120, 130, 140, 150];
  const yValues = [7, 8, 8, 9, 9, 9, 10, 11, 14, 14, 15];

  ctx = document.getElementById('Revenue-chart') as HTMLCanvasElement;
  new Chart(ctx, {
    type: "line",
    data: {
      labels: xValues,
      datasets: [{
        backgroundColor: "#4193ea",
        borderColor: "rgba(0,0,255,0.1)",
        data: yValues
      }]
    },
    options: {
      plugins: {
        title: {
          display: true,
          text: 'Revenue Earning'
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
#Revenue-chart {
  width: 100% !important;
  height: 100% !important;
}

#data {
  margin-right: 50px;
}

@media (max-width: 900px) {
  #Revenue-content {
    display: flex;
    flex-direction: column;
  }

  #Revenue-left #data {
    flex-direction: row;
    width: 100%;
  }

}
</style>