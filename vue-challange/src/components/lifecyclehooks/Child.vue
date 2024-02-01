<script setup>
import {onMounted, inject, onUnmounted} from "vue"

  const timer = inject('timer')
  const count = inject('count')

  onMounted(() => {
    console.log(`component mounted.`)
    timer.value = window.setInterval(() => {
      count.value++
    }, 1000)
  })

  onUnmounted(() => {
    console.log(`component unmounted`);
    window.clearInterval(timer.value)
  })
</script>

<template>
  <div>
    <p>
      Child Component: {{ count }}
    </p>
  </div>
</template>

<style scoped>

</style>