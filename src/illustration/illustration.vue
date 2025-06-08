<script setup>
  import MainHeader from "@/illustration/MainHeader.vue";
  import Ivana from "@/assets/img/illustration/page1/main.jpg";
  import Gaia from "@/assets/img/illustration/page2/main.jpg";
  import MainCharater from "@/assets/img/illustration/page3/main.jpg";
  import Oasis1 from "@/assets/img/illustration/page4/main.jpg";
  import Oasis2 from "@/assets/img/illustration/page5/main.jpg";
  import Oasis3 from "@/assets/img/illustration/page6/Oasis_design.jpg";
</script>

<template>
  <MainHeader></MainHeader>

  <h1>作品一覧</h1>
  <div class="wrapper_main">
    <h2><a href="#/illust_page1"><img class="subimg" :src="Ivana" /><br>Ivana</a></h2>
    <h2><a href="#/illust_page2"><img class="subimg" :src="Gaia"  /><br>Gaia</a></h2>
    <h2><a href="#/illust_page3"><img class="subimg" :src="MainCharater"  /><br>主人公</a></h2>
    <h2><a href="#/illust_page4"><img class="subimg" :src="Oasis1"  /><br>Oasis-1</a></h2>
    <h2><a href="#/illust_page5"><img class="subimg" :src="Oasis2"  /><br>Oasis-2</a></h2>
    <h2><a href="#/illust_page6"><img class="subimg" :src="Oasis3"  /><br>Oasisデザイン</a></h2>
  </div>

  <h1><a href="#/">←Back</a></h1> 
  
</template>

<style>
.subimg{
  height: 600px;
  width: 400px;
  object-fit: cover;
}
.wrapper_main {
  display: grid;
  grid-template-columns: repeat(3, 1fr); /* 自動で均等3列 */
  gap: 10px; /* カラム間のスペース（任意） */
  justify-content: center; /* グリッド全体を中央寄せ（任意） */
}
</style>