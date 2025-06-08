<script setup>
    import MainImage from "@/assets/img/illustration/page3/main.jpg";
    import sub1 from "@/assets/img/illustration/page3/sub1.jpg";
    import sub2 from "@/assets/img/illustration/page3/sub2.jpg";
    import sub3 from "@/assets/img/illustration/page3/sub3.jpg";
    import sub4 from "@/assets/img/illustration/page3/sub4.jpg";


</script>

<template>
    <div class="waku">
        <div class="setumei">
            <h1>主人公</h1>
            <p>概要</p>
            <p>物語のスポットライトにいる主人公を描いた。最初のラフはスーパーマンのような金髪、青い目の男性を想像して描いていたが、
                物語の設定でキャラクターの憂鬱を表現したかったので、陽気な金髪とくるくるの髪の毛を少しツンツンの茶髪にした。青い目をやめた理由も、
                彼は悲しげで戸惑った表情をしているが、その胸には確固たる意志が宿っていることを表すため。<br>
            また描き始めた時には彩度が低めの色を選んだが、少し暗すぎて調整した。</p>
            <p>制作にかかった期間</p>
            <p>〜1週間</p>
            <p>キャラクター設定</p>
            <p>海軍出身の彼は、除隊を機に故郷へ戻ってきた。彼は誠実で心優しい性格だが、口下手であまり多くを語らない。</p>

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
.Mainimg{
    height: 800px;
    object-fit: cover;
    width: 100%;
    padding: 0;
    margin: 0;
    transform: translateX(100px);
}
.subimg{
  height: 600px;
  width: 400px;
  object-fit: cover;
}
.waku{
  display: grid;
  grid-template-columns: 50% 50%;
}
.setumei {
  margin-left: -100px;
}
.wrapper {
  display: grid;
  grid-template-columns: 60% 30%;
  transform: translateX(-20px);
}
</style>