<template>
  <div class="book-reader">
    <h2 class="book-title">{{ $singleBook.title }}</h2>
    <div class="swiper-container mySwiper">
      <div class="swiper-wrapper">
        <div
          v-for="page in $singleBook.pages"
          :key="page.id"
          class="swiper-slide"
          v-html="page.text"
        ></div>
      </div>
      <div class="swiper-button-next"></div>
      <div class="swiper-button-prev"></div>
      <div class="swiper-pagination"></div>
    </div>
  </div>
</template>

<script lang="ts">
import Vue from 'vue'
import { books } from '@/store'

import 'swiper/swiper.scss'
import 'swiper/components/pagination/pagination.min.css'
import 'swiper/components/navigation/navigation.min.css'
import 'swiper/swiper-bundle.css'
import Swiper from 'swiper/swiper-bundle.min.js'

export default Vue.extend({
  computed: {
    $singleBook() {
      return books.$single
    },
  },

  mounted() {
    const swiper = new Swiper('.mySwiper', {
      pagination: {
        el: '.swiper-pagination',
        type: 'progressbar',
      },
      navigation: {
        nextEl: '.swiper-button-next',
        prevEl: '.swiper-button-prev',
      },
    })
  },
})
</script>
<style lang="scss" scoped>
.book-title {
  font-size: 1.5rem;
}

.swiper-container {
  width: 100%;
  height: 100%;
}

.swiper-slide {
  min-height: 1050px;
  /* text-align: center; */
  font-size: 18px;
  background: #fff;
  display: block;
  /* justify-content: center; */
  /* align-items: center; */
  padding: 70px 60px;
}

.swiper-slide img {
  display: block;
  width: 100%;
  height: 100%;
  object-fit: cover;
}

.mySwiper {
  border: 1px solid #cecece;
  box-shadow: 0px 5px 14px 2px #4c4c4c3d;
}

.book-reader {
  display: grid;
  grid-template-columns: 1fr;
  grid-gap: 2rem;
  align-items: center;
  @include screen('small', 'medium') {
    grid-template-columns: 1fr;
    grid-gap: 2rem;
  }
}
</style>
