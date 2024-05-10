<template>
  <WidgetPanel title="直流侧电流检测">
    <div ref="continer" class="widget-statistics-chart"></div>
  </WidgetPanel>
</template>
<script setup lang="ts">
import highcharts from 'highcharts'
import highcharts3d from 'highcharts/highcharts-3d'
import { onMounted, ref } from 'vue'
import WidgetPanel from '../WidgetPanel.vue'

highcharts3d(highcharts)
const continer = ref()
onMounted(() => {
  const options: any = {
    credits: { enabled: false },
    chart: {
      renderTo: continer.value,
      type: 'line',
      backgroundColor: 'rgba(0,0,0,0)',
      options3d: {
        enabled: true,
        alpha: 5,
        beta: 20,
        depth: 0,
        viewDistance: 25,
      },
    },
    xAxis: {
      categories: [
        '2024/06/04 12:00',
        '2024/06/05 12:00',
        '2024/06/06 12:00',
        '2024/06/07 12:00',
        '2024/06/08 12:00',
        '2024/06/09 12:00',
        '2024/06/10 12:00',
        '2024/06/11 12:00',
        '2024/06/12 12:00',
      ],
      tickWidth: 0,
      gridLineWidth: 0,
      left: '10px',
      labels: {
        style: {
          color: '#8fe3fd',
          fontSize: '10px',
        },
      },
    },
    yAxis: {
      visible: false,
      left: '10px',
    },
    tooltip: {
      pointFormat: '直流侧电流: {point.y}A',
    },
    title: {
      text: '',
    },
    legend: {
      enabled: false,
    },
    plotOptions: {

      line: {
        depth: 20,
        borderColor: '',
        dataLabels: {
          borderWidth: 0,
          enabled: true,
          color: '#8fe3fd',
          style: {
            fontSize: '8px',
          },
          // @ts-ignore
          formatter() {
            // @ts-ignore
            return `${this.y}`
          },
        },
      },
    },
    series: [
      {
        data: [22.1, 23.2, 22.2, 22.5, 22.6, 22.4, 23.1, 21.9, 22.2],
        colorByPoint: true,
      },
    ],
  }
  const chart = new highcharts.Chart(options)
})
</script>
<style lang="scss" scoped>
.widget-statistics-chart {
  width: 100%;
  height: 100%;

  // background-color: red;
}
</style>
