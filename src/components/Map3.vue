<script setup lang="ts"></script>

<template>
  <div class="map3"></div>
</template>

<style scoped>
.map3 {
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
  width: 7.075rem;
  height: 7.075rem;
  background: url('@/assets/image/jt.png');
  animation: rotate2 10s linear infinite;
  opacity: 0.6;
  background-size: 100% 100%;
}
@keyframes rotate2 {
  form {
    transform: translate(-50%, -50%) rotate(0deg);
  }
  to {
    transform: translate(-50%, -50%) rotate(-360deg);
  }
}
</style>
