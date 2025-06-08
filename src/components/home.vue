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

<style>
.subimg{
  height: 400px;
  width: 400px;
  object-fit: cover;
}
.wrapper_home {
  display: grid;
  grid-template-columns: repeat(3, 1fr); /* 自動で均等3列 */
  gap: 10px; /* カラム間のスペース（任意） */
  justify-content: center; /* グリッド全体を中央寄せ（任意） */
}
</style>