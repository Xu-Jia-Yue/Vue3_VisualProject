<script setup lang="ts">
import * as echarts from 'echarts'
import { onMounted } from 'vue'
import { randomColor } from '@/util/UseRandomColor'

onMounted(() => {
  const myChart = echarts.init(document.getElementById('pie2'))
  myChart.setOption({
    color: [
      randomColor(),
      randomColor(),
      randomColor(),
      randomColor(),
      randomColor(),
      randomColor(),
      randomColor(),
      randomColor()
    ],
    tooltip: {
      trigger: 'item',
      formatter: '{a} <br/>{b} : {c} ({d}%)'
    },
    grid: {
      left: '1',
      top: '1%',
      right: '1',
      bottom: '0%',
      containLabel: true
    },
    legend: {
      bottom: '0%',
      itemWidth: 10,
      itemHeight: 10,
      textStyle: {
        color: 'rgba(255,255,255,.5)',
        fontSize: '12'
      }
    },
    series: [
      {
        name: '地区分布',
        type: 'pie',
        radius: ['10%', '70%'],
        center: ['50%', '50%'],
        roseType: 'radius',
        label: {
          fontSize: 10
        },
        labelLine: {
          length: 6,
          length2: 8
        },
        data: [
          { value: 26, name: '北京' },
          { value: 24, name: '山东' },
          { value: 20, name: '江苏' },
          { value: 25, name: '浙江' },
          { value: 30, name: '四川' },
          { value: 42, name: '湖北' }
        ]
      }
    ]
  })
  // 监听浏览器缩放，图表对象调用缩放resize函数
  window.addEventListener("resize", function() {
    myChart.resize();
  })
})
</script>

<template>
  <div id="pie2"></div>
</template>

<style lang="scss" scoped>
#pie2 {
  width: 100%;
  height: 2.5rem;
}
</style>
