<script setup>
</script>

<template>
  <div class="glass-container">
    <nav class="left-nav">
      <div class="name">
        <a class="item" href="#">Ryovik</a>
      </div>

      <div class="items">
        <a class="item" href="#">Favorites</a>
        <a class="item" href="#">Code</a>
        <a class="item" href="#">Game</a>
        <a class="item" href="#">Music</a>
        <a class="item" href="#">Books</a>
      </div>
    </nav>

    <nav class="right-nav">
      <a class="item" href="#">
        <img src="@/assets/images/icons/github.png" />
      </a>
      <a class="item" href="#">
        <img src="@/assets/images/icons/bilibili.png" />
      </a>
      <a class="item" href="#">
        <img src="@/assets/images/icons/微信.png" />
      </a>
      <a class="item" href="#">
        <img src="@/assets/images/icons/小红书.png" />
      </a>
    </nav>
  </div>
</template>

<!--glass-container css-->
<style scoped>
.glass-container {
  position: fixed;

  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 0 50px;

  z-index: 2;

  top: 0;
  left: 0;
  right: 0;

  height: 65px;

  /* 半透明白色 */
  background: rgba(255, 255, 255, 0.1);
  /* 玻璃味道↑ */
  backdrop-filter: blur(15px) saturate(120%) brightness(110%);
  /* 阴影 */
  /*box-shadow: 0 4px 20px rgba(0, 0, 0, 0.3);*/
}
</style>

<!--General style css-->
<style scoped>
.left-nav,
.right-nav {
  display: flex;
  gap: 10px;
}
</style>

<!--left-nav css-->
<style scoped>
.left-nav{
  /*background-color: red;*/

  gap:35px;
}

.left-nav .items{
  display: flex;
}

.left-nav .item {
  width: 100px;
  height: 50px;

  font-size: 20px;
}

.left-nav .name a{
  font-weight: bold;
  font-size: 25px;
}

.left-nav .item {
  /*background-color: red;*/
  color: white;
  display: flex;
  justify-content: center; /* 水平居中 */
  align-items: center; /* 垂直居中 */
}
</style>

<!--right-nav css-->
<style scoped>
.right-nav .item {
  width: 35px;
  height: 35px;
}

.right-nav .item img {
  width: 100%;
  height: 100%;
}
</style>
