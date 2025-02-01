<template>
  <div class="character-list">
    <div v-for="character in sortedCharacters" :key="character.rank" class="character-item mb-3">
      <div class="d-flex p-3">
        <div class="character-image-wrapper">
          <img :src="character.image" :alt="character.name" class="character-image rounded-circle">
        </div>
        <div class="ms-3">
          <div class="d-flex align-items-center">
            <span class="badge bg-warning text-dark me-2">{{ character.rank }}</span>
            <h3>{{ character.name }}</h3>
          </div>
          <p>Hero Name: {{ character.heroName }}</p>
          <p>Ability: {{ character.ability }}</p>
          <p>Birthday: {{ character.birthday }}</p>
        </div>
      </div>
    </div>
  </div>
</template>

<script setup>
defineProps({
  sortedCharacters: {
    type: Array,
    required: true
  }
});
</script>

<style scoped>
.character-image-wrapper {
  width: 120px;
  height: 120px;
  overflow: hidden;
}

.character-image {
  width: 100%;
  height: 100%;
  object-fit: cover;
}
</style>
