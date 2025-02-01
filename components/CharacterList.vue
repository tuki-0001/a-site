<template>
  <div>
    <div v-for="character in sortedCharacters" :key="character.rank" class="character-card">
      <!-- キャラクター画像 -->
      <img :src="getImageUrl(character.image)" :alt="character.name" class="rounded-circle" style="width: 120px; height: 120px; object-fit: cover; margin-right: 20px;">
      <!-- キャラクターの名前 -->
      <h3>{{ character.name }}</h3>
      <!-- ヒーロー名 -->
      <p><strong>Hero Name:</strong> {{ character.heroName }}</p>
      <!-- 能力 -->
      <p><strong>Ability:</strong> {{ character.ability }}</p>
      <!-- 誕生日 -->
      <p><strong>Birthday:</strong> {{ character.birthday }}</p>
      <!-- 学校 -->
      <p><strong>School:</strong> {{ character.school }}</p>
      <!-- 前の学校 -->
      <p><strong>Former School:</strong> {{ character.formerSchool }}</p>
      <!-- 身長 -->
      <p><strong>Height:</strong> {{ character.height }}</p>
      <!-- 血液型 -->
      <p><strong>Blood Type:</strong> {{ character.bloodType }}</p>
      <!-- 好きなもの -->
      <p><strong>Likes:</strong> {{ character.likes }}</p>
      <!-- 性格 -->
      <p><strong>Personality:</strong> {{ character.personality }}</p>
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
