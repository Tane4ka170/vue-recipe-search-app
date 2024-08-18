<template>
  <header class="bg-white shadow h-16 flex justify-between items-stretch">
    <router-link
      :to="{ name: 'home' }"
      class="inline-flex items-center h-full px-5 text-gray-500 font-bold"
      >Home</router-link
    >
    <div class="flex items-center gap-1">
      <router-link
        :to="{ name: 'byName' }"
        class="px-2 h-full transition-colors hover:bg-gray-500 inline-flex items-center hover:text-white"
        >Search Meals</router-link
      >
      <router-link
        :to="{ name: 'byLetter' }"
        class="px-2 h-full transition-colors hover:bg-gray-500 inline-flex items-center hover:text-white"
        >Meals by letter</router-link
      >
      <router-link
        :to="{ name: 'ingredients' }"
        class="px-2 h-full transition-colors hover:bg-gray-500 inline-flex items-center hover:text-white"
        >Meals by ingredients</router-link
      >
    </div>
  </header>
</template>
