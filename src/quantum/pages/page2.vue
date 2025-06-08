<script setup>
    import sub1 from "@/assets/img/quantum/NOLTA1.pdf";
    import sub2 from "@/assets/img/quantum/NOLTA2.pdf";
    import sub3 from "@/assets/img/quantum/workshop.pdf";

</script>

<template>
  <div class="waku">
    <div class="setumei">
        <h1>概要</h1>
        <p>学会発表の原稿などを載せる。</p>
    </div>

    <div class="pdf">
      <p class="caption">2025年6月13日のNOLTAソサエティ大会の発表原稿</p>
      <iframe class="subimg" :src="sub1"></iframe>
      <p class="caption">2025年6月13日のNOLTAソサエティ大会の発表スライド</p>
      <iframe class="subimg" :src="sub2"></iframe>
      <p class="caption">2024年12月21日の非線形ワークショップの発表ポスター</p>
      <iframe class="subimg" :src="sub3"></iframe>
    </div>

  <h1 class="back-button"><a href="#/quantum">←Back</a></h1>
  </div>
</template>

<style scoped>
.setumei{
  text-align: left;
}
.subimg {
  width: 1000px;
  height: 1000px;
  object-fit: contain;
  text-align: center;
}
.pdf {
  margin-bottom: 3rem;
  text-align: center;
}
.waku{
  display: grid;
}
.back-button {
  position: fixed;
  bottom: 20px;      /* 画面下から20px上に配置 */
  left: 50%;         /* 横幅の真ん中 */
  transform: translateX(-50%); /* 自分の幅の半分だけ左にずらす */
  background-color: white;  /* 背景色（必要なら） */
  padding: 10px 20px;
  border-radius: 5px;
  box-shadow: 0 0 5px rgba(0,0,0,0.3);
  z-index: 1000;      /* 重なり優先度 */
  cursor: pointer;
  font-size: 1.2rem;
  text-align: center;
}

.back-button a {
  text-decoration: none;
  color: black;
}

</style>