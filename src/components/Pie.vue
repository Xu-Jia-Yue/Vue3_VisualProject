<script setup lang="ts">
import * as echarts from 'echarts'
import { onMounted } from 'vue'
import { randomColor } from '@/util/UseRandomColor'

onMounted(() => {
  const myChart = echarts.init(document.getElementById('pie'))
  myChart.setOption({
    color: [randomColor(), randomColor(), randomColor(), randomColor(), randomColor()],
    tooltip: {
      trigger: 'item',
      formatter: '{a} <br/>{b}: {c} ({d}%)'
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
        name: '年龄分布',
        type: 'pie',

        radius: ['40%', '60%'],
        center: ['50%', '45%'],
        avoidLabelOverlap: false,
        label: {
          show: false,
          position: 'center'
        },
        labelLine: {
          show: false
        },
        data: [
          { value: 1, name: '18岁以下' },
          { value: 4, name: '20-29岁' },
          { value: 2, name: '30-39岁' },
          { value: 2, name: '40-49岁' },
          { value: 1, name: '50岁以上' }
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
  <div id="pie"></div>
</template>

<style lang="scss" scoped>
#pie {
  width: 100%;
  height: 2.5rem;
}
</style>
