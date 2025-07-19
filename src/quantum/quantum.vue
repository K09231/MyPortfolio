<script setup>
  import MainHeader from "@/illustration/MainHeader.vue";
  import research from "@/assets/img/quantum/Dwave.jpeg";
  import conference from "@/assets/img/quantum/conference.jpg";

</script>

<template>
  <MainHeader></MainHeader>

  <h1>作品一覧</h1>

  <div class="wrapper_main">
    <div class="item">
      <a href="#/quantum_page1">
        <img class="subimg" :src="research" />
        <h2>研究内容（作成コードや実験結果など）</h2>
      </a>
    </div>
    <div class="item">
      <a href="#/quantum_page2">
        <img class="subimg" :src="conference" />
        <h2>学会発表</h2>
      </a>
    </div>
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