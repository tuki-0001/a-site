<template>
  <div>
    <div v-for="character in sortedCharacters" :key="character.id" class="character-card">
      <img :src="getImageUrl(character.image)" :alt="character.name" class="rounded-circle" style="width: 120px; height: 120px; object-fit: cover; margin-right: 20px;">
      <h3>{{ character.name }}</h3>
      <p><strong>Hero Name:</strong> {{ character.heroName }}</p>
      <p><strong>Ability:</strong> {{ character.ability }}</p>
      <p><strong>Birthday:</strong> {{ character.birthday }}</p>
    </div>
  </div>
</template>

<script setup>
import { defineProps } from 'vue';

const props = defineProps({
  sortedCharacters: {
    type: Array,
    required: true,
    default: () => [],
  },
});

const getImageUrl = (image) => {
  return image ? require(`@/assets/img/${image}`) : require('@/assets/default-image.jpg');
};
</script>
