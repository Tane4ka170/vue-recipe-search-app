<script setup>
import { computed } from "vue";
import store from "../store";
import { RouterLink } from "vue-router";

const letters = "ABCDEFGHIJKLMNPQRSTUVWXYZ".split("");
</script>

<template>
  <div class="flex p-8 flex-col">
    <input
      type="text"
      class="rounded border-2 border-slate-200 w-full"
      placeholder="Search for meals"
    />

    <div class="flex gap-2 justify-center mt-2">
      <RouterLink
        :to="{ name: 'byLetter', params: { letter } }"
        v-for="letter of letters"
        :key="letter"
        >{{ letter }}</RouterLink
      >
    </div>
  </div>
</template>
