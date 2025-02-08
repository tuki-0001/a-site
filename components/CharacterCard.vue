<template>
  <div class="card mb-4" style="max-width: 540px;">
    <div class="row g-0">
      <!-- キャラクター画像 -->
      <div class="col-md-4" @click="showProfile">
        <img 
          :src="getImageUrl(character.image)" 
          :alt="character.name" 
          class="img-fluid rounded-start" 
          style="object-fit: cover; height: 120px;" 
        />
      </div>

      <div class="col-md-8">
        <div class="card-body">
          <!-- ランク表示 -->
          <h6 class="card-subtitle mb-2 text-muted">Rank: {{ character.rank }}</h6>
          
          <!-- キャラクターの名前 -->
          <h5 class="card-title">{{ character.name }}</h5>

          <!-- ヒーローかヴィランかで表示内容を変更 -->
          <p class="card-text">
            <strong>{{ character.heroName ? 'ヒーロー名' : 'ヴィラン名' }}:</strong>
            {{ character.heroName || character.villainName }}
          </p>

          <!-- 詳細情報 -->
          <p class="card-text" v-if="showDetails"><strong>能力:</strong> {{ character.ability }}</p>
          <p class="card-text" v-if="showDetails"><strong>誕生日:</strong> {{ character.birthday }}</p>
          <p class="card-text" v-if="showDetails"><strong>学校:</strong> {{ character.school }}</p>
          <p class="card-text" v-if="showDetails"><strong>前の学校:</strong> {{ character.formerSchool }}</p>
          <p class="card-text" v-if="showDetails"><strong>身長:</strong> {{ character.height }}</p>
          <p class="card-text" v-if="showDetails"><strong>血液型:</strong> {{ character.bloodType }}</p>
          <p class="card-text" v-if="showDetails"><strong>好きなもの:</strong> {{ character.likes }}</p>
          <p class="card-text" v-if="showDetails"><strong>性格:</strong> {{ character.personality }}</p>
        </div>
      </div>
    </div>
  </div>
</template>

<script setup>
import { ref } from 'vue';

// 親コンポーネントから渡される character オブジェクトを受け取る
const props = defineProps({
  character: {
    type: Object,
    required: true,
  },
});

// プロフィール情報を表示するための状態
const showDetails = ref(false);

// 画像クリックでプロフィール情報を表示
const showProfile = () => {
  showDetails.value = !showDetails.value;
};

// 画像パスを取得する関数
const getImageUrl = (image) => {
  if (image) {
    return image;
  } else {
    return '/img/default-image.jpg';
  }
};
</script>
