<script setup>
import { ref } from "vue";
import axiosClient from "../axiosClient";

const keyword = ref("");
function searchMeals() {}
</script>

<template>
  <div class="p-8">
    <input
      type="text"
      v-model="keyword"
      class="rounded border-2 border-slate-200 w-full"
      placeholder="Search for meals"
      @change="searchMeals"
    />
  </div>
</template>
