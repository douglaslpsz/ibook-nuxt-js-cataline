<template>
  <div class="book-cover">
    <img :src="$book.cover" :alt="`Capa do livro ${$book.title}`" />
    <NuxtLink class="read-book" :to="`/book/${$book.id}/read`" >
      Ler livro
    </NuxtLink>
  </div>
</template>

<script lang="ts">
  import Vue from 'vue'
  import { books } from '~/store'

  export default Vue.extend({
    computed: {
      $book() {
        return books.$single
      }
    }
  })
</script>

<style lang="scss" scoped>
.book-cover {
  img {
    width: 100%;
  }
  .read-book {
    background: #292929;
    color: #f7f7f7;
    text-transform: uppercase;
    font-weight: 700;
    width: 100%;
    height: 42px;
    font-size: 1.1rem;
    display: grid;
    justify-content: center;
    align-items: center;
    transition: all 300ms ease;
    &:hover {
      transition: all 70ms ease;
      -webkit-box-shadow: inset 0 0 0 3px #246ec2!important;
      box-shadow: inset 0 0 0 3px #246ec2!important;
    }
    &:active {
      transition: all 70ms ease;
      opacity: 0.89;
      -webkit-box-shadow: inset 0 0 0 3px #246ec2!important;
      box-shadow: inset 0 0 0 3px #246ec2!important;
    }
  }
}
</style>