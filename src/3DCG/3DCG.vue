<script setup>
  import MainHeader from "@/illustration/MainHeader.vue";
  import blender from "@/assets/img/3DCG/blender.png";
  import maya from "@/assets/img/3DCG/maya_boar.png";
</script>

<template>
  <MainHeader></MainHeader>

  <h1>作品一覧</h1>
  <div class="wrapper_main">
    <h2><a href="#/3DCG_page1"><img class="subimg" :src="blender" /><br>Blender</a></h2>
    <h2><a href="#/3DCG_page2"><img class="subimg" :src="maya"  /><br>Maya</a></h2>
  </div>

  <h1><a href="#/">←Back</a></h1> 
  
</template>

<style scoped>
.subimg {
  width: 100%;
  max-width: 400px;
  height: auto;
  aspect-ratio: 2 / 3;
  object-fit: cover;
  display: block;
  margin: 0 auto;
}

.wrapper_main {
  display: grid;
  grid-template-columns: repeat(3, 1fr);  /* デフォルト：3列 */
  gap: 20px;
  justify-items: center;
  max-width: 1300px;
  margin: 0 auto;
  padding: 20px;
}

/* タブレット画面：2列 */
@media (max-width: 1024px) {
  .wrapper_main {
    grid-template-columns: repeat(2, 1fr);
  }
}

/* スマホ画面：1列 */
@media (max-width: 600px) {
  .wrapper_main {
    grid-template-columns: 1fr;
  }
}
</style>