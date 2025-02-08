<template>
  <div class="text-center mb-5" style="background: url('/img/default-image.jpg') no-repeat top center; background-size: 100% auto; padding: 120px 0; color: white; border-radius: 15px;">
    <h2 class="display-4 font-weight-bold" style="text-shadow: 2px 2px 4px rgba(0, 0, 0, 0.5);">{{ title }}</h2>
    <p class="lead" style="font-size: 1.3rem; text-shadow: 1px 1px 4px rgba(0, 0, 0, 0.5);">{{ subtitle }}</p>
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
