<script setup>
import { computed, onMounted, watch } from "vue";
import { useRoute } from "vue-router";
import MealItem from "../components/MealItem.vue";
import { useStore } from "vuex";

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

    <div class="grid grid-cols-1 md:grid-cols-3 gap-5 p-8">
      <MealItem v-for="meal of meals" :key="meal.idMeal" :meal="meal" />
    </div>
  </div>
</template>
