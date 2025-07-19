<script setup>
    import MainImage from "@/assets/img/illustration/page6/Oasis_design.jpg";
    import sub1 from "@/assets/img/illustration/page6/Oasis_back.jpg";
    import sub2 from "@/assets/img/illustration/page6/Oasis_front.jpg";
    import sub3 from "@/assets/img/illustration/page6/Oasis_side.jpg";


</script>

<template>
    <div class="waku">
        <div class="setumei">
            <h1>Oasisデザイン（三面図）</h1>
            <p>概要</p>
            <p>モデリングのため三面図を作成した。服装はOasis-2のものにした。全体デザインに「Finel」と書いてあるが、それは彼女の本名。
                「Oasis」というニックネームを付けた理由は、彼女はまさに主人公が嵐のただ中で見つけた「オアシス」。
            </p>
            <p>制作にかかった期間</p>
            <p>〜1週間</p>
            <p>キャラクター設定</p>
            <p>Oasisの衣装は、フォーマルドレスを基にデザインした。ドレスの側面には蛇のような形状をした金属装飾をあしらい、彼女のしなやかな体のラインを美しく際立たせている。
                誰が「医者は白衣しか着られない」と言ったのでしょう？今、彼女は部屋の片隅に静かに立っている。
                音楽が流れはじめました――どうか、彼女にダンスの誘いを。きっと、彼女は少し驚きながらも、微笑んで手を取ってくれるでしょう。</p>

    <div class="wrapper">
        <div><img class="subimg" :src="sub1"/><br>後ろ</div>
        <div><img class="subimg" :src="sub2"/><br>前</div>
        <div><img class="subimg" :src="sub3"/><br>横</div>
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
