<script setup lang="ts"></script>

<template>
  <div class="map2"></div>
</template>

<style scoped>
.map2 {
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
  width: 8.0375rem;
  height: 8.0375rem;
  background: url('@/assets/image/lbx.png');
  animation: rotate1 15s linear infinite;
  opacity: 0.6;
  background-size: 100% 100%;
}
@keyframes rotate1 {
  form {
    transform: translate(-50%, -50%) rotate(0deg);
  }
  to {
    transform: translate(-50%, -50%) rotate(360deg);
  }
}
</style>
