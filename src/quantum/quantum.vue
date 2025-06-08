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
  height: 400px;
  width: 400px;
  object-fit: cover;
  display: block;
  margin: 0 auto;
}

.wrapper_main {
  display: grid;
  grid-template-columns: repeat(2, 1fr);
  gap: 40px;
  justify-items: center;
  margin: 2rem auto;
  max-width: 1000px;
  text-align: center;
}

.item {
  width: 100%;
}

.item p {
  margin-top: 0.5rem;
  font-size: 1.2rem;
}

</style>