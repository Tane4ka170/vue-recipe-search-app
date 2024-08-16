<script setup>
import Navbar from "../components/Navbar.vue";
</script>

<template>
  <div class="bg-slate-100 h-full">
    <navbar />
    <main><router-view /></main>
  </div>
</template>
