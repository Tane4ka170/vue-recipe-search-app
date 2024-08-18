<script setup>
import { computed, onMounted, watch } from "vue";
import { useRoute } from "vue-router";
import { useStore } from "vuex";
import Meals from "../components/Meals.vue";

const route = useRoute();
const store = useStore();
const letters = "ABCDEFGHIJKLMNPQRSTUVWXYZ".split("");
const meals = computed(() => store.state.mealsByLetter);

watch(route, () => {
  store.dispatch("searchMealsByLetter", route.params.letter);
});

onMounted(() => {
  store.dispatch("searchMealsByLetter", route.params.letter);
});
</script>

<template>
  <div>
    <div class="flex gap-2 justify-center mt-2">
      <RouterLink
        :to="{ name: 'byLetter', params: { letter } }"
        v-for="letter of letters"
        :key="letter"
        >{{ letter }}</RouterLink
      >
    </div>

    <Meals :meals="meals" />
  </div>
</template>
