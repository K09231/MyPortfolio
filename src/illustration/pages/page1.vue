<script setup>
    import MainImage from "@/assets/img/illustration/page1/main.jpg";
    import sub1 from "@/assets/img/illustration/page1/sub1.jpg";
    import sub2 from "@/assets/img/illustration/page1/sub2.jpg";
    import sub3 from "@/assets/img/illustration/page1/sub3.jpg";
    import sub4 from "@/assets/img/illustration/page1/sub4.jpg";


</script>

<template>
    <div class="waku">
        <div class="setumei">
            <h1>Ivana</h1>
            <p>概要</p>
            <p>目をつぶって女性のキャラクターを描いてみたら、彼女はいた。目の下と、口の隣にほくろがある。</p>
            <p>制作にかかった期間</p>
            <p>〜1週間</p>
            <p>キャラクター設定</p>
            <p>すべての感情が彼女の中で増幅されている。彼女は愛するもののために全力を尽くす。決して彼女の手を離さないで。</p>

    <div class="wrapper">
        <div><img class="subimg" :src="sub1"/><br>ラフ</div>
        <div><img class="subimg" :src="sub2"/><br>顔の描き込み</div>
        <div><img class="subimg" :src="sub3"/><br>髪の毛の描き込み</div>
        <div><img class="subimg" :src="sub4"/><br>アクセサリーの描き込み</div>
    </div>
        </div>
        <div>
            <img class="Mainimg" :src="MainImage" />
        </div> 
    </div>
    
    


    <h1><a href="#/illustration">←Back</a></h1> 
</template>

<style scoped>
.waku {
  display: grid;
  grid-template-columns: 1fr 1fr; /* 左右2分割 */
  gap: 20px;
  align-items: start;
}

.setumei {
  padding: 20px;
}

.wrapper {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 10px;
  margin-top: 20px;
}

/* メイン画像 */
.Mainimg {
  width: 100%;
  padding: 0;
  margin: 0;
  height: 800px;
  object-fit: cover;
  display: block;

}

/* サブ画像 */
.subimg {
  width: 100%;
  height: auto;
  max-width: 300px;
  object-fit: cover;
}

/* ======= レスポンシブ対応 ========== */
@media (max-width: 768px) {
  .waku {
    grid-template-columns: 1fr;
  }

  .Mainimg {
    order: 2;
    max-width: 100%;
    height: 500px;
  }

  .setumei {
    order: 1;
  }
}
</style>
