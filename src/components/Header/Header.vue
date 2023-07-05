<template>
  <div class="menu flex flex-justify-around full-width">
    <a href="https://yandex.ru/" class="menu-item flex flex-center cursor-pointer no-decoration">
      Яndex
    </a>
    <a href="https://google.com/" class="menu-item flex flex-center cursor-pointer  no-decoration">
      Google
    </a>
  </div>
</template>

<script setup lang="ts">

</script>

<style lang="scss">
.menu {
  background: rgba(0, 81, 255, 0.14);
  height: 80px;
}

.menu-item {
  font-weight: bold;
  font-size: 16px;
}
</style>