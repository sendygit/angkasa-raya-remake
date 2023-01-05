<script setup>
import TheHeader from "@/components/TheHeader.vue";
</script>

<template>
  <header id="home" class="">
    <TheHeader />
  </header>
  <main id="articles" class="px-20">
    <!-- <router-view /> -->
  </main>
  <footer></footer>
</template>

<style>
html {
  scroll-behavior: smooth;
}
body {
  background-color: black;
  color: white;
  overflow-x: hidden;
}
/* 
header {
  position: relative;
  width: 100%;
  height: 100vh;
  display: flex;
  flex-direction: column;
  background: url(@/assets/jumbotron.jpg);
  background-size: cover;
  background-position: center;
} */
</style>
