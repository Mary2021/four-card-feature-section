<script setup lang="ts">
import CardSection from '../components/CardSection.vue'
import { ref } from 'vue'
let componentKey = ref(0)

screen.orientation.addEventListener('change', async () => {
  const forceRerender = async () => {
    componentKey.value += 1
  }
  forceRerender()
})
</script>

<template>
  <CardSection :key="componentKey" />
</template>
