<script setup>
import { reactive } from 'vue'

//粒子数量
const count = 300

// 创建单个粒子函数
const createParticle = () => ({
  x: Math.random() * 99,
  size: 6 + Math.random() * 10,
  duration: 8 + Math.random() * 6,
  delay: Math.random() * 6,
})

// 数组粒子
const particles = reactive(Array.from({ length: count }, createParticle))
</script>

<template>
  <div class="particles-container">
    <div
      class="particle"
      v-for="(p, i) in particles"
      :key="i"
      :style="{
        left: p.x + '%',
        width: p.size + 'px',
        height: p.size + 'px',
        animationDuration: p.duration + 's',
        animationDelay: p.delay + 's',
      }"
    ></div>
  </div>
</template>

<!--particles-container-->
<style scoped>
.particles-container {
  position: absolute;
  inset: 0;
  z-index: 1;
}
</style>

<!--particle-->
<style scoped>
.particle {
  position: absolute;
  bottom: 0px;

  background-color: red;
  opacity: 0;
  border-radius: 50%;

  /*动态覆盖*/
  left: 0%;
  width: 0px;
  height: 0px;

  animation-name: up_float;
  /*动态覆盖*/
  animation-duration: 0s;
  animation-timing-function: linear;
  /*动态覆盖*/
  animation-delay: 0s;
  animation-iteration-count: infinite;
}

@keyframes up_float {
  0% {
    opacity: 0;
    transform: translateY(0);
  }
  50% {
    opacity: 1;
    transform: translateY(-50vh);
  }
  100% {
    opacity: 0;
    transform: translateY(-100vh);
  }
}
</style>
