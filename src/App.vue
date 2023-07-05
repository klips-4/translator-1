<template>
  <div class="main__wrapper full-screen">
   <Header/>
    <div class="content full-width">
      <main-page/>
    </div>
  </div>
</template>

<script setup lang="ts">
import MainPage from "./components/pages/mainPage.vue";
import Header from "./components/Header/Header.vue";

</script>
<style src="./assets/style.scss">

</style>
