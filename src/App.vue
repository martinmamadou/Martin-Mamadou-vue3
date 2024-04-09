<script setup>
import { RouterLink, RouterView } from 'vue-router'
import HomeView from './views/HomeView.vue';
import HeaderComponent from './components/HeaderComponent.vue';
import FooterComp from './components/FooterComp.vue'
</script>

<template>
    <HeaderComponent />
  <RouterView />
  <FooterComp />
</template>

<style scoped>

</style>
