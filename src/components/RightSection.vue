<script setup>
</script>

<template>
  <section class="right">
    <header class="header-container">
      <h1 class="title">self-introduction</h1>
      <p class="subtitle">Learning front-end development · motion effects and accessibility</p>
    </header>

    <section class="section-container">
      <p>你好，我是 Ryovik。正在用 Vue 做一个一页式个人名片，专注于视觉动画和组件化。</p>
      <p>近期在做：玻璃拟态卡片、渐进动效、响应式布局。也在学习 Git/GitHub 的协作流程。</p>
      <p>技能关键词：HTML/CSS/JS、Vue 3、Grid/Flex、过渡与性能（只动画 transform/opacity）。</p>
    </section>

    <footer class="footer-container">
      <button class="flip-btn" type="button" aria-label="查看背面">反转背面</button>
    </footer>
  </section>
</template>

<style scoped>
.right {
  display: grid;

  grid-template-rows: 1fr 2fr 1fr;
  grid-template-columns: 1fr;

  height: 100%;   /* 让它吃满外层这一列的高度 */
  min-height: 0;  /* 允许子项在网格里收缩 */
  gap: 0;         /* 有需要再加行间距 */

  position: relative;
}
.right::before{
  content: '';

  position: absolute;

  height: 2px;
  background: linear-gradient(to right, transparent, rgba(255, 255, 255, 0.5), transparent);
  /*background-color: red;*/

  top:25%;
  left: 10%;
  right: 10%;
}

.right .header-container{
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

.header-container{
  display: flex;
  flex-direction: column;
  justify-content: center;
}
.header-container .title{
  /*background-color: yellow;*/
  font-size: 2rem;
}
.header-container .subtitle{
  /*background-color: #fff;*/
  font-size: 1rem;
}

.footer-container .flip-btn{
  position: absolute;
  right: 20px;
  bottom: 20px;

  width: 110px;
  height: 35px;
  border-radius: 10px;
}
</style>
