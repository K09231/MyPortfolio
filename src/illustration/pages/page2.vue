<script setup>
    import MainImage from "@/assets/img/illustration/page2/main.jpg";
    import sub1 from "@/assets/img/illustration/page2/sub1.jpg";
    import sub2 from "@/assets/img/illustration/page2/sub2.jpg";
    import sub3 from "@/assets/img/illustration/page2/sub3.jpg";
    import sub4 from "@/assets/img/illustration/page2/sub4.jpg";


</script>

<template>
    <div class="waku">
        <div class="setumei">
            <h1>Gaia</h1>
            <p>概要</p>
            <p>二次創作。最初は赤髪（ginger）を描きたかったが、なぜか彼女に黒髪のほうが似合うともって修正した。</p>
            <p>制作にかかった期間</p>
            <p>〜1週間</p>
            <p>キャラクター設定</p>
            <p>冷たいが優しい女性を想定してイラストを作成した。画面全体の彩度が低いが、目玉だけの彩度を高め、<br>
                人の視線を奪うポイントになる。</p>

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