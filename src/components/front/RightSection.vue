<script setup>
// 声明props
const { header, section } = defineProps({
  header: Object,
  section: Array,
})

// 声明emit
const emit = defineEmits(['flip']);

function flipCard(){
  emit('flip', true);
}

</script>

<template>
  <section class="right">
    <header class="header-container">
      <h1 class="title">{{ header.title }}</h1>
      <p class="subtitle">{{ header.subtitle }}</p>
    </header>

    <section class="section-container">
      <p v-for="(p, i) in section" :key="i">{{ p }}</p>
    </section>

    <footer class="footer-container">
      <button @click="flipCard" class="flip-btn" type="button" aria-label="查看背面">翻转背面</button>
    </footer>
  </section>
</template>

<style scoped>
.right {
  display: grid;

  grid-template-rows: 1fr 2fr 1fr;
  grid-template-columns: 1fr;

  height: 100%; /* 让它吃满外层这一列的高度 */
  min-height: 0; /* 允许子项在网格里收缩 */
  gap: 0; /* 有需要再加行间距 */

  position: relative;
}
.right::before {
  content: '';

  position: absolute;

  height: 2px;
  background: linear-gradient(to right, transparent, rgba(255, 255, 255, 0.5), transparent);
  /*background-color: red;*/

  top: 25%;
  left: 10%;
  right: 10%;
}

.right .header-container {
  /*background-color: red;*/
  padding-left: 20px;
}
.right .section-container {
  /*background-color: green;*/
  padding: 20px 20px;
}
.right .footer-container {
  /*background-color: blue;*/

  position: relative;
}

.header-container {
  display: flex;
  flex-direction: column;
  justify-content: center;
}
.header-container .title {
  /*background-color: yellow;*/
  font-size: 2rem;
}
.header-container .subtitle {
  /*background-color: #fff;*/
  font-size: 1rem;
}

.footer-container .flip-btn {
  position: absolute;
  right: 20px;
  bottom: 20px;

  width: 110px;
  height: 35px;

  border-radius: 10px;
}
.footer-container .flip-btn:hover{
  cursor: pointer;
}
</style>
