<script setup>
import { Navigation, Pagination } from "swiper";
import { Swiper, SwiperSlide } from "swiper/vue";
import { ref } from "vue";
import merkurius from "@/assets/merkurius.png";
import venus from "@/assets/venus.png";
import bumi from "@/assets/bumi.png";
import mars from "@/assets/mars.png";
import jupiter from "@/assets/jupiter.png";
import saturnus from "@/assets/saturnus.png";
import uranus from "@/assets/uranus.png";
import neptunus from "@/assets/neptunus.png";

import "swiper/css";
import "swiper/css/navigation";
import "swiper/css/pagination";

const arrowPrev = ref(null);
const arrowNext = ref(null);

const datas = [
  {
    title: "MERKURIUS",
    desc: "Merkurius adalah planet terkecil di Tata Surya sekaligus yang terdekat dari Matahari. Periode revolusi planet ini merupakan yang terpendek dari semua planet di Tata Surya, yakni 87,79 hari.Seperti halnya Venus, Merkurius merupakan planet inferior yang letak orbitnya berada di sebelah dalam orbit Bumi.",
    img: merkurius,
  },
  {
    title: "VENUS",
    desc: "Venus adalah planet terdekat kedua dari Matahari setelah Merkurius. Planet ini mengorbit Matahari selama 224,7 hari Bumi. Venus tidak memiliki satelit alami. Tekanan atmosfer permukaan Venus 92 kali lebih besar daripada Bumi. Dengan rata-rata suhu permukaan sebesar 735 K (462 °C; 863 °F).",
    img: venus,
  },
  {
    title: "BUMI",
    desc: "Bumi adalah planet ketiga dari Matahari yang merupakan planet terpadat dan terbesar kelima dari delapan planet dalam Tata Surya. Bumi terbentuk sekitar 4,54 miliar tahun yang lalu, dan kehidupan sudah muncul di permukaannya paling tidak sekitar 3,5 miliar tahun yang lalu.",
    img: bumi,
  },
  {
    title: "MARS",
    desc: "Mars adalah planet terdekat keempat dari Matahari. Planet ini sering dijuluki sebagai 'planet merah'. Ini disebabkan oleh keberadaan besi oksida di permukaan planet Mars. Planet ini memiliki 2 buah satelit, yaitu Fobos dan Deimos. Planet ini mengorbit selama 687 hari dalam mengelilingi Matahari.",
    img: mars,
  },
  {
    title: "JUPITER",
    desc: "Jupiter adalah planet terdekat kelima dari Matahari setelah Merkurius, Venus, Bumi, dan Mars. Planet ini juga merupakan planet terbesar di Tata Surya. Jupiter merupakan raksasa gas dengan massa seperseribu massa Matahari dan dua setengah kali jumlah massa semua planet lain di Tata Surya.",
    img: jupiter,
  },
  {
    title: "SATURNUS",
    desc: "Saturnus adalah planet keenam dari Matahari dan merupakan planet terbesar kedua di Tata Surya setelah Jupiter. Saturnus terkenal dengan sistem cincinnya yang unik, yang sebagian besar terdiri dari partikel-partikel es dengan sedikit puing-puing batu dan debu.Setidaknya diketahui ada 82 satelit alami yang mengorbit",
    img: saturnus,
  },
  {
    title: "URANUS",
    desc: "Uranus adalah planet ketujuh dari Matahari. Uranus merupakan planet yang memiliki jari-jari terbesar ketiga sekaligus massa terbesar keempat di Tata Surya Komposisi Uranus serupa dengan Neptunus, dan keduanya mempunyai komposisi kimiawi yang berbeda dari raksasa gas yang lebih besar, Jupiter dan Saturnus.",
    img: uranus,
  },
  {
    title: "NEPTUNUS",
    desc: "Neptunus merupakan planet terjauh (kedelapan) jika ditinjau dari Matahari. Neptunus merupakan planet terbesar keempat berdasarkan diameter (49.530 km) dan terbesar ketiga berdasarkan massa. Neptunus mengorbit Matahari pada jarak 30,1 sa atau sekitar 4.450 juta km.",
    img: neptunus,
  },
];
</script>

<template>
  <div>
    <h1 class="text-center text-6xl mt-24 mb-6">TATA SURYA</h1>
  </div>
  <div class="px-24">
    <swiper
      :slides-per-view="1"
      :space-between="50"
      :navigation="{
        prevEl: arrowPrev,
        nextEl: arrowNext,
      }"
      :pagination="{ Pagination }"
      :modules="[Navigation]"
    >
      <swiper-slide v-for="data in datas" :key="data.title">
        <div class="flex flex-col items-center">
          <img :src="data.img" alt="" class="h-80" />
          <h1 class="text-4xl font-bold mt-4">{{ data.title }}</h1>
          <p class="text-lg mt-4 text-center">
            {{ data.desc }}
          </p>
        </div>
      </swiper-slide>
    </swiper>
  </div>
  <div class="relative bottom-44">
    <button class="absolute left-0" ref="arrowPrev">
      <h1 class="text-4xl">&#10094;</h1>
    </button>
    <button class="absolute right-0" ref="arrowNext">
      <h1 class="text-4xl">&#10095;</h1>
    </button>
  </div>
</template>
