<script setup>
  import HeaderImage from "@/assets/img/headerMain.jpg";
  import IconImage from "@/assets/img/icon.png";
  const headerImage = HeaderImage
</script>

<template>
    <header class="header">
     <img class="headerimg" :src="HeaderImage" style="width: 100%;" />
     <section class="profile-preview">
      <img class="Iconimage" :src="IconImage" style="height: 100.2px;" /> Finlay K
     </section>
     <br>
     <a href="#/">Home</a> <a href="#/profile">プロフィール</a>
  </header>
</template>

<style>


</style>
