<template>
  <div class="title-wrapper text-center mb-5">
    <h2 class="title">僕のヒーローアカデミア キャラランキング</h2>
    <p class="subtitle">魅力的なキャラたち、ここに集結！</p>
  </div>
</template>

<script setup>
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
