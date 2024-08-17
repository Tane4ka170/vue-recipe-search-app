<script setup>
import { computed, onMounted, ref } from "vue";
import { useRoute } from "vue-router";
import { useStore } from "vuex";
import Meals from "../components/Meals.vue";

const keyword = ref("");
const store = useStore();
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
      class="rounded border-2 border-slate-200 w-full bg-white"
      placeholder="Search for meals"
      @change="searchMeals"
    />
  </div>
  <Meals :meals="meals" />
</template>
