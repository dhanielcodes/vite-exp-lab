<template>
  <div>
    <img :src="img" alt="">
    <h1 v-for="(item, index) in im" :key="index">
      {{item.name}}
    </h1>
  </div>
</template>

<script setup>
import {ref} from 'vue'
    export const img = ref(null)
    export const im = ref([])

    fetch('https://jsonplaceholder.typicode.com/users')
  .then(response => response.json())
  .then(data => {
    im.value = data
  })
</script>
