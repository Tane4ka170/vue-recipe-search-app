<script setup>
const props = defineProps({
  href: String,
});
</script>

<template>
  <a
    :href="href"
    target="_blank"
    class="px-3 py-2 rounded border-2 border-gray-600 bg-gray-500 hover:bg-gray-600 transition-colors text-white"
  >
    <slot></slot>
  </a>
</template>
