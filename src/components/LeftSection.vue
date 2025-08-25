<script setup>

</script>

<template>
  <aside class="left">
    <figure class="profile">
      <img src="@/assets/images/profile_photo.jpg" alt="头像" />
      <figcaption class="name">Ryovik</figcaption>
    </figure>

    <nav class="links-container">
      <ul class="links">
        <li class="link">
          <a href="#">
            <img src="@/assets/images/icons/微信.png" />
            <p>微信公众号</p>
          </a>
        </li>
        <li class="link">
          <a href="#">
            <img src="@/assets/images/icons/steam.png" />
            <p>Steam</p>
          </a>
        </li>
        <li class="link">
          <a href="#">
            <img src="@/assets/images/icons/bilibili.png" />
            <p>BiliBili</p>
          </a>
        </li>
      </ul>
    </nav>
  </aside>
</template>

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
