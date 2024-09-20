<script setup lang="ts">
import * as echarts from 'echarts'
import { onMounted } from 'vue'
import { randomColor } from '@/util/UseRandomColor'

onMounted(() => {
  const myChart = echarts.init(document.getElementById('line'))
  myChart.setOption({
    color: [randomColor(), randomColor()],
    tooltip: {
      trigger: 'axis'
    },
    legend: {
      textStyle: {
        color: '#4c9bfd'
      },
      right: '10%'
    },
    grid: {
      top: '15%',
      left: '3%',
      right: '4%',
      bottom: '1%',
      show: true,
      borderColor: '#012f4a',
      containLabel: true
    },

    xAxis: {
      type: 'category',
      boundaryGap: false,
      data: ['1月', '2月', '3月', '4月', '5月', '6月', '7月', '8月', '9月', '10月', '11月', '12月'],
      axisTick: {
        show: false
      },
      axisLabel: {
        color: '#4c9bfd'
      },
      axisLine: {
        show: false
      }
    },
    yAxis: {
      type: 'value',
      axisTick: {
        show: false
      },
      axisLabel: {
        color: '#4c9bfd'
      },
      axisLine: {
        show: false
      },
      splitLine: {
        lineStyle: {
          color: '#012f4a'
        }
      }
    },
    series: [
      {
        name: '转行率',
        type: 'line',
        smooth: true,
        data: [24, 40, 101, 134, 90, 230, 210, 230, 120, 230, 210, 120]
      },
      {
        name: '离职率',
        type: 'line',
        smooth: true,
        data: [40, 64, 191, 324, 290, 330, 310, 213, 180, 200, 180, 79]
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
  <div id="line"></div>
</template>

<style lang="scss" scoped>
#line {
  width: 100%;
  height: 2.5rem;
}
</style>
