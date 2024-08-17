<script setup>
const props = defineProps({
  href: String,
});
</script>

<template>
  <a
    :href="href"
    target="_blank"
    class="px-3 py-2 rounded border-2 border-zinc-600 bg-zinc-500 hover:bg-zinc-600 transition-colors text-white"
  >
    <slot></slot>
  </a>
</template>
