<template>
  <ReaderTemplate />
</template>

<script lang="ts">
  import Vue from 'vue'
  import { books } from '@/store'

  export default Vue.extend({
    layout: 'ibook',
    async asyncData( {params} ) {
      await books.show({ id: params.id as any})
      console.log(books.$single)
    },
    head() {
      return{
        title: `${books.$single.title} - Leitura`,
        meta: [
          {
            hid: 'description',
            name: 'description',
            content: books.$single.description
          }
        ]
      }
    }
  })
</script>

<style scoped>
</style>