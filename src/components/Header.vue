<script setup lang="ts">
import dayjs from 'dayjs'
import { onMounted, ref } from 'vue'

const nowDay = ref(dayjs().format('YYYY年MM月DD日 - hh时mm分ss秒')) as any
onMounted(() => {
  setInterval(() => {
    nowDay.value = dayjs().format('YYYY年MM月DD日 - hh时mm分ss秒')
  }, 1000)
})
</script>

<template>
  <!-- 头部的盒子 -->
  <header>
    <h1>数据可视化-ECharts</h1>
    <div class="showTime">当前时间： {{ nowDay }}</div>
  </header>
</template>

<style lang="scss" scoped>
header {
  position: relative;
  height: 1rem;
  background: url('@/assets/image/head_bg.png') no-repeat;
  background-size: 100% 100%;
  h1 {
    font-size: 0.475rem;
    color: #fff;
    text-align: center;
    line-height: 1rem;
  }
  .showTime {
    position: absolute;
    right: 0.375rem;
    top: 0;
    line-height: 0.9375rem;
    color: rgba(255, 255, 255, 0.7);
    font-size: 0.25rem;
  }
}
</style>
