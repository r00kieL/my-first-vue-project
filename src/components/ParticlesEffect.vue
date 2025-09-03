<script setup>
import { reactive } from 'vue'

//粒子数量
const count = 30

// 创建单个粒子函数
const createParticle = () => ({
  x: Math.random() * 90,
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
        '--x': p.x + '%',
        '--size': p.size + 'px',
        '--duration': p.duration + 's',
        '--delay': p.delay + 's',
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

  --x: 0%;
  --size: 8px;
  --duration: 10s;
  --delay: 0s;

  left: var(--x);
  width: var(--size);
  height: var(--size);

  animation-name: up_float;
  animation-duration: var(--duration);
  animation-timing-function: linear;
  animation-delay: var(--delay);
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
