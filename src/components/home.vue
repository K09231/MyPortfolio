<script setup>
  import MainHeader from "@/components/MainHeader.vue";
  import Ivana from "@/assets/img/illustration/page4/main.jpg";
  import Quantum from "@/assets/img/quantum/quantum.jpg";
  import modeling from "@/assets/img/3DCG/blender.png"; // ここを3DCGの画像に変更
</script>

<template>
  <MainHeader></MainHeader>

  <h1>作品一覧</h1>
  <div class="wrapper_home">
    <h2><a href="#/illustration"><img class="subimg" :src="Ivana" /><br>イラストレーション</a></h2>
    <h2><a href="#/quantum"><img class="subimg" :src="Quantum" /><br>量子コンピュータ（研究）</a></h2>
    <h2><a href="#/3DCG"><img class="subimg" :src="modeling" /><br>3DCG</a></h2>
  </div>
  
</template>

<style scoped>
.subimg {
  width: 100%;
  height: auto;
  max-width: 400px;
  min-height: 600px;
  aspect-ratio: 3/4;
  object-fit: cover;
  display: block;
  margin: 0 auto;
}

.wrapper_home {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  gap: 20px;
  justify-items: center;
  max-width: 1200px;
  margin: 0 auto;
  padding: 20px;
}

/* タブレット以下で2列にする */
@media (max-width: 1024px) {
  .wrapper_home {
    grid-template-columns: repeat(2, 1fr);
  }
}

/* スマホでは1列に */
@media (max-width: 600px) {
  .wrapper_home {
    grid-template-columns: 1fr;
  }
}

</style>