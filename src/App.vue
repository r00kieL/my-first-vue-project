<!--<script setup>-->
<!--import { RouterLink, RouterView } from 'vue-router'-->
<!--import HelloWorld from './components/HelloWorld.vue'-->
<!--</script>-->

<!--<template>-->
<!--  <header>-->
<!--    <img alt="Vue logo" class="logo" src="@/assets/logo.svg" width="125" height="125" />-->

<!--    <div class="wrapper">-->
<!--      <HelloWorld msg="You did it!" />-->

<!--      <nav>-->
<!--        <RouterLink to="/">Home</RouterLink>-->
<!--        <RouterLink to="/about">About</RouterLink>-->
<!--      </nav>-->
<!--    </div>-->
<!--  </header>-->

<!--  <RouterView />-->
<!--</template>-->

<!--<style scoped>-->
<!--header {-->
<!--  line-height: 1.5;-->
<!--  max-height: 100vh;-->
<!--}-->

<!--.logo {-->
<!--  display: block;-->
<!--  margin: 0 auto 2rem;-->
<!--}-->

<!--nav {-->
<!--  width: 100%;-->
<!--  font-size: 12px;-->
<!--  text-align: center;-->
<!--  margin-top: 2rem;-->
<!--}-->

<!--nav a.router-link-exact-active {-->
<!--  color: var(&#45;&#45;color-text);-->
<!--}-->

<!--nav a.router-link-exact-active:hover {-->
<!--  background-color: transparent;-->
<!--}-->

<!--nav a {-->
<!--  display: inline-block;-->
<!--  padding: 0 1rem;-->
<!--  border-left: 1px solid var(&#45;&#45;color-border);-->
<!--}-->

<!--nav a:first-of-type {-->
<!--  border: 0;-->
<!--}-->

<!--@media (min-width: 1024px) {-->
<!--  header {-->
<!--    display: flex;-->
<!--    place-items: center;-->
<!--    padding-right: calc(var(&#45;&#45;section-gap) / 2);-->
<!--  }-->

<!--  .logo {-->
<!--    margin: 0 2rem 0 0;-->
<!--  }-->

<!--  header .wrapper {-->
<!--    display: flex;-->
<!--    place-items: flex-start;-->
<!--    flex-wrap: wrap;-->
<!--  }-->

<!--  nav {-->
<!--    text-align: left;-->
<!--    margin-left: -1rem;-->
<!--    font-size: 1rem;-->

<!--    padding: 1rem 0;-->
<!--    margin-top: 1rem;-->
<!--  }-->
<!--}-->
<!--</style>-->

<script></script>

<template>
  <main class="glass-container">
    <aside class="left">
      <figure class="profile">
        <img src="@/assets/images/profile_photo.jpg" alt="头像" />
        <figcaption class="name">Ryovik</figcaption>
      </figure>

      <nav class="links-container">
        <ul class="links">
          <li class="link">
            <a href="#">
              <img src="@/assets/images/icons/微信.svg" />
              <p>微信公众号</p>
            </a>
          </li>
          <li class="link">
            <a href="#">
              <img src="@/assets/images/icons/steam.svg" />
              <p>Steam</p>
            </a>
          </li>
          <li class="link">
            <a href="#">
              <img src="@/assets/images/icons/哔哩哔哩.svg" />
              <p>BiliBili</p>
            </a>
          </li>
        </ul>
      </nav>
    </aside>

    <section class="right">
      <header class="header-container">
        <h1 class="title">self-introduction</h1>
        <p class="subtitle">Learning front-end development · Love motion effects and accessibility</p>
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
  </main>
</template>

<!--left and right area css-->
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

<!--profile css-->
<style scoped>
.profile {
  /*background-color: green;*/

  display: flex;
  align-items: center;

  margin: 20px;
  gap: 30px;
}

.profile img {
  border-radius: 50%;

  height: 100px;
  width: 100px;

  object-fit: cover;
}

.profile .name {
  font-size: 25px;
  font-weight: bold;
  color: white;
}
</style>

<!--links and link css-->
<style scoped>
.links-container .links {
  /*background-color: green;*/

  display: flex;

  flex-direction: column;
  gap: 10px;

  align-content: flex-start;
}

.links .link {
  /*background-color: red;*/

  width: 200px;
  height: 80px;
}

.link a {
  height: 100%;

  display: flex;
  justify-content: space-around;
  align-items: center;

  transition:
    transform 0.18s ease,
    filter 0.18s ease;
}

.link img {
  display: block;

  width: 50px;
  height: 50px;

  object-fit: contain;
}

.link p {
  font-weight: bold;
  color: white;
}

.link a {
  transition: transform 0.5s ease;
}
.link a:hover {
  transform: translateY(-10px);

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
}
</style>
