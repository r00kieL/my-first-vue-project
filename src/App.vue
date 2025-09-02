<script setup>
//-----引入vue内置功能-----
import { reactive, ref } from 'vue'

// -----引入组件-----
import LeftSection from '@/components/LeftSection.vue'
import RightSection from '@/components/RightSection.vue'

// -----引入组件数据-----
import { profile, links } from '@/data/componentsData/leftSectionData.js'
import { header, section } from '@/data/componentsData/rightSectionData.js'
// -----转换成响应式-----
const profileState = reactive(profile)
const linksState = reactive(links)
const headerState = reactive(header)
const sectionState = reactive(section)

// 按钮翻转的响应式变量
const isFlipped = ref(false)
</script>

<template>
  <main class="card-container">
    <div class="card-rotator" :class="{ 'card-rotator--flipped': isFlipped }">
      <section class="card-container-front">
        <LeftSection :profile="profileState" :links="linksState" />

        <RightSection
          @flip="(msg) => (isFlipped = msg)"
          :header="headerState"
          :section="sectionState"
        />
      </section>

      <section class="card-container-back">


        这是背面这是背面这是背面这是背面这是背面这是背面这是背面这是背面这是
      </section>
    </div>
  </main>
</template>

<!--card-container css-->
<style scoped>
.card-container {
  height: 500px;
  width: 900px;

  position: relative;
  perspective: 1000px;
}
</style>

<!--card-rotator css--->
<style scoped>
.card-rotator {
  position: absolute;
  inset: 0;

  transform-style: preserve-3d;
  transition: transform 1s;
  /*transform: rotateY(180deg);*/
}
.card-rotator--flipped {
  transform: rotateY(180deg);
}
</style>

<!--card-container-front  and card-container-back css-->
<style scoped>
.card-container-front,
.card-container-back {
  inset: 0;
  position: absolute;

  backface-visibility: hidden;

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

<!--card-container-front css-->
<style scoped>
.card-container-front {
  overflow: hidden;

  display: grid;
  grid-template-columns: 30% 70%;
}

.card-container-front::before {
  content: '';

  position: absolute;

  width: 2px;

  background: linear-gradient(to bottom, transparent, rgba(255, 255, 255, 0.5), transparent);

  left: 30%;
  top: 10%;
  bottom: 10%;
}
</style>

<!--card-container-back css-->
<style scoped>
.card-container-back {
  transform: rotateY(180deg);
}
</style>
