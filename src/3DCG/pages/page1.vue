<script setup>
    import sub1 from "@/assets/img/3DCG/sealion.png";
    import sub2 from "@/assets/img/3DCG/glass.png";
    import sub3 from "@/assets/img/3DCG/pawn.png";


</script>

<template>
    <div class="waku">
        <div class="setumei">
            <h1>概要</h1>
            <p>Blnderでオブジェクト作成に関する基本操作を習った。</p>

            <div class="wrapper">
              <div><img class="subimg" :src="sub1"/><br>アザラシ</div>
              <div><img class="subimg" :src="sub2"/><br>ワイングラス</div>
              <div><img class="subimg" :src="sub3"/><br>チェス</div>
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