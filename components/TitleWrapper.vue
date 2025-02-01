<template>
  <div class="title-wrapper text-center mb-5">
    <h2 class="title">{{ title }}</h2>
    <p class="subtitle">{{ subtitle }}</p>
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
.title {
  font-size: 3rem;
  font-weight: bold;
}

.subtitle {
  font-size: 1.25rem;
  color: #666;
  margin-top: 10px;
}

/* レスポンシブ対応 */
@media (max-width: 768px) {
  .title {
    font-size: 2rem;
  }

  .subtitle {
    font-size: 1rem;
  }
}
</style>
