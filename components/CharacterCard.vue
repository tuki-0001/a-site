<template>
  <div class="card mb-4" style="max-width: 540px;">
    <div class="row g-0">
      <!-- キャラクター画像 -->
      <div class="col-md-4">
        <img 
          :src="getImageUrl(character.image)" 
          :alt="character.name" 
          class="img-fluid rounded-start" 
          style="object-fit: cover; height: 120px;" 
        />
      </div>
      <div class="col-md-8">
        <div class="card-body">
          <!-- キャラクターの名前 -->
          <h5 class="card-title">{{ character.name }}</h5>

          <!-- ヒーローかヴィランかで表示内容を変更 -->
          <p class="card-text">
            <strong>{{ character.heroName ? 'ヒーロー名' : 'ヴィラン名' }}:</strong>
            {{ character.heroName || character.villainName }}
          </p>

          <!-- 詳細情報 -->
          <p class="card-text" v-if="character.ability"><strong>能力:</strong> {{ character.ability }}</p>
          <p class="card-text" v-if="character.birthday"><strong>誕生日:</strong> {{ character.birthday }}</p>
          <p class="card-text" v-if="character.school"><strong>学校:</strong> {{ character.school }}</p>
          <p class="card-text" v-if="character.formerSchool"><strong>前の学校:</strong> {{ character.formerSchool }}</p>
          <p class="card-text" v-if="character.height"><strong>身長:</strong> {{ character.height }}</p>
          <p class="card-text" v-if="character.bloodType"><strong>血液型:</strong> {{ character.bloodType }}</p>
          <p class="card-text" v-if="character.likes"><strong>好きなもの:</strong> {{ character.likes }}</p>
          <p class="card-text" v-if="character.personality"><strong>性格:</strong> {{ character.personality }}</p>

        </div>
      </div>
    </div>
  </div>
</template>

<script setup>
import { defineProps } from 'vue';

// 親コンポーネントから渡される character オブジェクトを受け取る
const props = defineProps({
  character: {
    type: Object,
    required: true,
  },
});

// 画像パスを取得する関数
const getImageUrl = (image) => {
  // 画像が指定されていれば、その画像を返す
  if (image) {
    return image;
  } else {
    // 画像が指定されていなければ、デフォルト画像を返す
    return '/img/default-image.jpg';
  }
};
</script>


