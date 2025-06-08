<script setup>
    import sub1 from "@/assets/img/3DCG/boar.png";
    import sub2 from "@/assets/img/3DCG/texture1.png";
    import sub3 from "@/assets/img/3DCG/texture2.png";
    import sub4 from "@/assets/img/3DCG/boar_UV1.png";
    import sub5 from "@/assets/img/3DCG/boar_UV2.png";

</script>

<template>
    <div class="waku">
        <div class="setumei">
            <h1>概要</h1>
            <p>Blnderを習う最中にいろいろ調べて、業界ではMayaというソフトはより広く使われていることを知り、Mayaを触り始めた。
              Mayaでオブジェクト作成に関する基本操作と、テクスチャーの貼り方（UV展開）を習った。
              これからはレンダリング、アニメーションやスクリプトについて触っていく予定。</p>

            <div class="wrapper">
              <div><img class="subimg" :src="sub1"/><br>イノシシの子</div>
              <div><img class="subimg" :src="sub2"/><br>バスダックのテクスチャー</div>
              <div><img class="subimg" :src="sub3"/><br>立方体のテクスチャー</div>
              <div><img class="subimg" :src="sub4"/><br>イノシシの子のテクスチャー貼り</div>
              <div><img class="subimg" :src="sub5"/><br>イノシシの子のUV展開</div>
            </div>
        </div>

    <h1><a href="#/3DCG">←Back</a></h1> 
  </div>
</template>

<style scoped>
.CIM {
  text-align: left; /* 明示的に文字は左揃え */
}

.wrapper {
  text-align: center; /* この中の要素を中央寄せ */
  margin: 20px 0;     /* 上下に余白（任意） */
}

.subimg {
  width: 800px;
  height: auto;
  object-fit: contain;
}
.waku{
  display: grid;
}

</style>