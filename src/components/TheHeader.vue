<script setup>
import { ref, onMounted } from "vue";

const stars = ref();
const ufo = ref();
const text = ref();

onMounted(() => {
  window.addEventListener("scroll", function () {
    let val = window.scrollY;
    stars.value.style.right = val * 0.25 + "px";
    ufo.value.style.top = val * -0.3 + "px";
    text.value.style.top = val * -0.7 + "px";
  });
});
</script>

<template>
  <nav class="z-50 relative fixed mt-6 px-24">
    <div class="flex items-center">
      <div class="fixed mt-10">
        <a href="#home" class="text-2xl"><img src="@/assets/logo.png" alt="" /></a>
      </div>

      <ul class="flex space-x-32 text-xl ml-auto mr-24">
        <li><a class="fixed" href="#home">Home</a></li>
        <li><a class="fixed" href="#articles">Articles</a></li>
        <li><a class="fixed" href="#about">About Us</a></li>
      </ul>
    </div>
  </nav>

  <div class="paralax relative flex z-40">
    <img
      class="absolute right-0 object-cover bg-repeat overflow-hidden"
      src="@/assets/stars.png"
      alt=""
      ref="stars"
    />
    <img class="absolute w-80 mt-120px left-[40%]" src="@/assets/ufo.png" alt="" ref="ufo" />
    <div class="text-6xl absolute left-[40%] mt-380px" ref="text">
      <h1>ANGKASA</h1>
    </div>
    <img src="@/assets/jumbotron.png" alt="" class="z-1000 absolute mb-28" />
  </div>
</template>

<style>
.layer {
  position: absolute;
  width: 100%;
  height: 60vh;
  bottom: 0;
  left: 0;
  background: linear-gradient(to top, rgb(0, 0, 0), rgba(0, 0, 0, 0));
}
nav ul li a::before {
  content: "";
  position: absolute;
  width: 100%;
  height: 1px;
  border-radius: 1px;
  background-color: rgb(255, 255, 255);
  bottom: 0;
  left: 0;
  transform-origin: right;
  transform: scaleX(0);
  transition: transform 0.3s ease-in-out;
}

nav ul li a:hover::before {
  transform-origin: left;
  transform: scaleX(1);
}
a {
  text-decoration: none;
  background-color: none;
  color: rgb(255, 255, 255);
}
</style>
