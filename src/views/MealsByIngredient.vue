<script setup>
import { computed, onMounted, ref } from "vue";
import axiosClient from "../axiosClient";
import MealItem from "../components/MealItem.vue";
import { useStore } from "vuex";
import { useRoute } from "vue-router";
import Meals from "../components/Meals.vue";

const store = useStore();
const meals = computed(() => store.state.mealsByIngredient);
const route = useRoute();

onMounted(() => {
  store.dispatch("searchMealsByIngredient", route.params.ingredient);
});
</script>

<template>
  <Meals :meals="meals" />
</template>
