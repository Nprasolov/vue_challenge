<!--<script setup>-->
<!--import HelloWorld from './components/HelloWorld.vue'-->
<!--import Child from "./components/lifecyclehooks/Child.vue";-->
<!--</script>-->

<!--<template>-->
<!--  <div>-->
<!--    <a href="https://vitejs.dev" target="_blank">-->
<!--      <img src="/vite.svg" class="logo" alt="Vite logo" />-->
<!--    </a>-->
<!--    <a href="https://vuejs.org/" target="_blank">-->
<!--      <img src="./assets/vue.svg" class="logo vue" alt="Vue logo" />-->
<!--    </a>-->
<!--  </div>-->
<!--  <HelloWorld msg="Vite + Vue" />-->
<!--  <Child></Child>-->
<!--</template>-->

<!--<style scoped>-->
<!--.logo {-->
<!--  height: 6em;-->
<!--  padding: 1.5em;-->
<!--  will-change: filter;-->
<!--  transition: filter 300ms;-->
<!--}-->
<!--.logo:hover {-->
<!--  filter: drop-shadow(0 0 2em #646cffaa);-->
<!--}-->
<!--.logo.vue:hover {-->
<!--  filter: drop-shadow(0 0 2em #42b883aa);-->
<!--}-->
<!--</style>-->
<script setup lang="ts">
import { ref, provide } from "vue"
import Child from "./components/lifecyclehooks/Child.vue";

const visible = ref(true)
const timer = ref(null)
const count = ref(0)
provide("timer", timer)
provide("count", count)

function toggle() {
  visible.value = !visible.value
}
</script>

<template>
  <div>
    <Child v-if="visible" />
    <p>
      <button @click="toggle">
        Toggle Child Component
      </button>
    </p>
  </div>
</template>