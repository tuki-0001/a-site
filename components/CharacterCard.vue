<template>
  <div class="card mb-4" style="max-width: 540px;">
    <div class="row g-0">
      <!-- キャラクター画像 -->
      <div class="col-md-4">
        <img :src="getImageUrl(character.image)" :alt="character.name" class="img-fluid rounded-start" style="object-fit: cover; height: 120px;">
      </div>
      <div class="col-md-8">
        <div class="card-body">
          <!-- キャラクターの名前 -->
          <h5 class="card-title">{{ character.name }}</h5>
          <p class="card-text"><strong>Hero Name:</strong> {{ character.heroName }}</p>
          <p class="card-text"><strong>Ability:</strong> {{ character.ability }}</p>
          <p class="card-text"><strong>Birthday:</strong> {{ character.birthday }}</p>
          <p class="card-text"><strong>School:</strong> {{ character.school }}</p>
          <p class="card-text"><strong>Former School:</strong> {{ character.formerSchool }}</p>
          <p class="card-text"><strong>Height:</strong> {{ character.height }}</p>
          <p class="card-text"><strong>Blood Type:</strong> {{ character.bloodType }}</p>
          <p class="card-text"><strong>Likes:</strong> {{ character.likes }}</p>
          <p class="card-text"><strong>Personality:</strong> {{ character.personality }}</p>
        </div>
      </div>
    </div>
  </div>
</template>

<script setup>
import { defineProps } from 'vue';

const props = defineProps({
  character: {
    type: Object,
    required: true,
  },
});

const getImageUrl = (image) => {
  // public/img フォルダ内の画像パスを直接返す
  return image ? `/img/${image}` : '/img/default-image.jpg'; // 画像が指定されていない場合はデフォルト画像を表示
};
</script>
