<template>
  <nav class="flex items-center justify-between p-4 shadow-md">
    <h1 class="text-xl font-bold text-blue-500">Testagram</h1>
    <button @click="$emit('toggleTheme')" class="text-gray-400 hover:text-white">
      {{ dark ? '🌙' : '☀️' }}
    </button>
  </nav>
</template>

<script lang="ts">
export default {
  props: {
    dark: Boolean
  }
};
</script>