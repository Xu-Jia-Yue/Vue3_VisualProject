<script setup lang="ts">
import * as echarts from 'echarts'
import { onMounted } from 'vue'
import { randomColor } from '@/util/UseRandomColor'

onMounted(() => {
  const myChart = echarts.init(document.getElementById('bar'))
  myChart.setOption({
    color: [randomColor()],
    tooltip: {
      trigger: 'axis',
      axisPointer: {
        type: 'shadow'
      }
    },
    grid: {
      left: '0%',
      top: '10px',
      right: '0%',
      bottom: '4%',
      containLabel: true
    },
    xAxis: [
      {
        type: 'category',
        data: ['旅游行业', '教育培训', '游戏行业', '医疗行业', '电商行业', '社交行业', '金融行业'],
        axisTick: {
          alignWithLabel: true
        },
        axisLabel: {
          color: 'rgba(255,255,255,.6) ',
          fontSize: '12'
        },
        axisLine: {
          show: false
        }
      }
    ],
    yAxis: [
      {
        type: 'value',
        axisLabel: {
          color: 'rgba(255,255,255,.6) ',
          fontSize: 12
        },
        axisLine: {
          lineStyle: {
            color: 'rgba(255,255,255,.1)',
            width: 2
          }
        },
        splitLine: {
          lineStyle: {
            color: 'rgba(255,255,255,.1)'
          }
        }
      }
    ],
    series: [
      {
        name: '直接访问',
        type: 'bar',
        barWidth: '35%',
        data: [200, 300, 300, 900, 1500, 1200, 600],
        itemStyle: {
          barBorderRadius: 5
        }
      }
    ]
  })
  // 监听浏览器缩放，图表对象调用缩放resize函数
  window.addEventListener('resize', function () {
    myChart.resize()
  })
})
</script>

<template>
  <div id="bar"></div>
</template>

<style lang="scss" scoped>
#bar {
  width: 100%;
  height: 2.5rem;
}
</style>
