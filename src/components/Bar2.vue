<script setup lang="ts">
import * as echarts from 'echarts'
import { onMounted } from 'vue'
import { randomColor } from '@/util/UseRandomColor'

onMounted(() => {
  const myChart = echarts.init(document.getElementById('bar2'))
  myChart.setOption({
    grid: {
      top: '10%',
      left: '22%',
      bottom: '10%'
    },
    xAxis: {
      show: false
    },
    yAxis: [
      {
        type: 'category',
        inverse: true,
        data: ['HTML5', 'CSS3', 'javascript', 'VUE', 'NODE'],
        axisLine: {
          show: false
        },
        axisTick: {
          show: false
        },
        axisLabel: {
          color: '#fff'
        }
      },
      {
        data: [702, 350, 610, 793, 664],
        inverse: true,
        axisLine: {
          show: false
        },
        axisTick: {
          show: false
        },
        axisLabel: {
          color: '#fff'
        }
      }
    ],
    series: [
      {
        name: '条',
        type: 'bar',
        data: [70, 34, 60, 78, 69],
        yAxisIndex: 0,
        itemStyle: {
          barBorderRadius: 20,
          color: function () {
            return randomColor()
          }
        },
        barCategoryGap: 50,
        barWidth: 10,
        label: {
          show: true,
          position: 'inside',
          formatter: '{c}%'
        }
      },
      {
        name: '框',
        type: 'bar',
        barCategoryGap: 50,
        barWidth: 15,
        yAxisIndex: 1,
        data: [100, 100, 100, 100, 100],
        itemStyle: {
          color: 'none',
          borderColor: '#00c1de',
          borderWidth: 3,
          barBorderRadius: 15
        }
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
  <div id="bar2"></div>
</template>

<style lang="scss" scoped>
#bar2 {
  width: 100%;
  height: 2.5rem;
}
</style>
