<script setup>
import { onMounted, ref } from 'vue'
import baseTitle from '@/components/baseTitle.vue'
import useAPI from '@/composables/useAPI'

const { categories, getCategories } = useAPI()

onMounted(async () => {
  await getCategories()
})


</script>

<template>
  <baseTitle>TRIVIA APPLICATION</baseTitle>
  <div v-for="category in categories" :key="category.id">
    {{ category.name }}
  </div>

</template>
