<script setup>
import LeftSection from '@/components/LeftSection.vue'
import RightSection from '@/components/RightSection.vue'
</script>

<template>
  <main class="glass-container">
    <left-section />

    <right-section />
  </main>
</template>

<!--glass-container css-->
<style scoped>
.glass-container {
  height: 500px;
  width: 900px;

  /* 玻璃味道↑ */
  backdrop-filter: blur(15px) saturate(120%) brightness(110%);
  /* 半透明白色 */
  background: rgba(255, 255, 255, 0.1);
  /* 圆角 */
  border-radius: 12px;
  /* 阴影 */
  box-shadow: 0 4px 20px rgba(0, 0, 0, 0.3);
  /* 细边 */
  border: 1px solid rgba(255, 255, 255, 0.18);
  /* 玻璃折射的第二道细线 */
  outline: 1px solid rgba(255, 255, 255, 0.06);

  overflow: hidden;

  display: grid;
  grid-template-columns: 30% 70%;

  position: relative;
}

.glass-container::before {
  content: '';

  position: absolute;

  width: 2px;

  background: linear-gradient(to bottom, transparent, rgba(255, 255, 255, 0.5), transparent);
  /*background-color: red;*/

  left: 30%;
  top: 10%;
  bottom: 10%;
}
</style>
