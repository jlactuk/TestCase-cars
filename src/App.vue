<script setup>
import Header from './components/Header.vue'
import Aside from './components/Aside.vue'
import Gallery from './components/Gallery.vue'
import { provide, ref } from 'vue'
const count = ref(100);
provide('countVechicles', count)


</script>

<template>
      <section class="screen">
        <Aside />
        <main>
        <Header />
        <Gallery />
      </main>
      </section>
   
</template>

<style scoped>
   .screen {
    display: grid;
    grid-template-columns: 256px 1fr;
    width: 100%;
    height: 100%;
  }
</style>
