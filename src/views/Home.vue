<script setup>
import { computed, onMounted, ref } from "vue";
import store from "../store";
import { RouterLink } from "vue-router";
import axiosClient from "../axiosClient";

const ingredients = ref([]);

onMounted(async () => {
  const response = await axiosClient.get("/list.php?i=list").then();
  ingredients.value = response.data;
});
</script>

<template>
  <div class="flex p-8 flex-col"></div>
</template>
