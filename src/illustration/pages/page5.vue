<script setup>
    import MainImage from "@/assets/img/illustration/page5/main.jpg";
    import sub1 from "@/assets/img/illustration/page5/sub1.jpg";
    import sub2 from "@/assets/img/illustration/page5/sub2.jpg";
    import sub3 from "@/assets/img/illustration/page5/sub3.jpg";
    import sub4 from "@/assets/img/illustration/page5/sub4.jpg";


</script>

<template>
    <div class="waku">
        <div class="setumei">
            <h1>Oasis-2</h1>
            <p>概要</p>
            <p>キャラクター「Oasis」の２作目のポートレート。初期のセンター分けの設定から、サイド分けと斜めの前髪に変更したのは、彼女が非常に知的な一面を持ちながらも、
                時には少しドジなところがあることを表現するため。
                そうすることで、彼女の外見があまり「硬く」見えないようにした。今回の描写では、彼女に「蛇」のようなイヤリングとペンダントを加えた。
                これは、彼女の過去に何か掘り下げるべき秘密があることを暗示している。そしてそれが、Oasis-1との間に見られる表情の違いの一因でもある。</p>
            <p>制作にかかった期間</p>
            <p>〜1週間</p>
            <p>キャラクター設定</p>
            <p>どうか、彼女にすべてを打ち明けてください。そう、すべて。
                彼女に隠し事をしないでください――彼女は、あなたの精神科医だから。</p>

    <div class="wrapper">
        <div><img class="subimg" :src="sub1"/><br>ラフ</div>
        <div><img class="subimg" :src="sub2"/><br>顔の描き込み</div>
        <div><img class="subimg" :src="sub3"/><br>髪の毛の描き込み</div>
        <div><img class="subimg" :src="sub4"/><br>全体調整</div>
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
