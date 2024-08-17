<script setup>
import { computed, onMounted, ref } from "vue";
import store from "../store";
import { useRoute } from "vue-router";

const keyword = ref("");
const meals = computed(() => store.state.searchedMeals);
const route = useRoute();

function searchMeals() {
  store.dispatch("searchMeals", keyword.value);
}

onMounted(() => {
  keyword.value = route.params.name;
  if (keyword.value) {
    searchMeals();
  }
});
</script>

<template>
  <div class="p-8 pb-0">
    <input
      type="text"
      v-model="keyword"
      class="rounded border-2 border-slate-200 w-full"
      placeholder="Search for meals"
      @change="searchMeals"
    />
  </div>
  <div class="grid grid-cols-1 md:grid-cols-3 gap-5 p-8">
    <div
      v-for="meal of meals"
      :key="meal.idMeal"
      class="bg-white shadow rounded-xl"
    >
      <router-link :to="{ name: 'mealDetails', params: { id: meal.idMeal } }"
        ><img
          :src="meal.strMealThumb"
          :alt="meal.strMeal"
          class="rounded-t-xl h-48 object-cover w-full"
      /></router-link>

      <div class="p-3">
        <h3 class="font-bold">{{ meal.strMeal }}</h3>
        <p class="mb-4">
          Lorem ipsum dolor sit amet consectetur adipisicing elit. Voluptate,
          explicabo.
        </p>
        <div class="flex items-center justify-between">
          <a
            :href="meal.strYoutube"
            target="_blank"
            class="px-3 py-2 rounded border-2 border-zinc-600 bg-zinc-500 hover:bg-zinc-600 transition-colors text-white"
            >YouTube</a
          >
        </div>
      </div>
    </div>
  </div>
</template>
