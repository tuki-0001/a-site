<template>
  <div class="text-center mb-5">
    <h2 class="display-4">{{ title }}</h2>
    <p class="lead">{{ subtitle }}</p>
  </div>
</template>

<script setup>
defineProps({
  title: {
    type: String,
    default: '僕のヒーローアカデミア キャラランキング',
  },
  subtitle: {
    type: String,
    default: '魅力的なキャラたち、ここに集結！',
  },
});
</script>