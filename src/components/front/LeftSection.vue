<script setup>
const {profile, links} = defineProps({
  profile: Object,
  links: Array,
})
</script>

<template>
  <aside class="left">
    <figure class="profile">
      <img :src="profile.avatar" alt="头像" />
      <figcaption class="name">{{ profile.name }}</figcaption>
    </figure>

    <nav class="links-container">
      <ul class="links">
        <li class="link" v-for="link in links" :key="link.id">
          <a :href=link.href>
            <img :src=link.icon />
            <p>{{link.name}}</p>
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

  /*!* 半透明白色 *!*/
  background: rgba(255, 255, 255, 0.1);
  /*!* 玻璃味道↑ *!*/
  backdrop-filter: blur(15px) saturate(120%) brightness(110%);
  /*!* 圆角 *!*/
  border-radius: 12px;
}
</style>
