<template>
  <div class="text-center mb-5" style="padding: 100px 0;">
    <h2 class="display-4 text-primary font-weight-bold animated fadeInUp">{{ title }}</h2>
    <p class="lead text-secondary animated fadeInUp" style="font-size: 1.3rem; animation-delay: 0.3s;">{{ subtitle }}</p>
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

<style scoped>
@keyframes fadeInUp {
  0% {
    opacity: 0;
    transform: translateY(30px);
  }
  100% {
    opacity: 1;
    transform: translateY(0);
  }
}

.animated {
  animation-duration: 1s;
  animation-timing-function: ease-out;
}
</style>
