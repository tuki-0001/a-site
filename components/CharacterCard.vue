<template>
  <div class="card mb-4" style="max-width: 540px; margin: 0 auto;">
    <div class="row g-0">
      <!-- キャラクター画像 -->
      <div class="col-12" @click="showProfile">
        <img 
          :src="getImageUrl(character.image)" 
          :alt="character.name" 
          class="img-fluid rounded-start" 
          style="object-fit: cover; height: 120px; width: 100%;" 
        />
      </div>

      <div class="col-12">
        <div class="card-body" style="max-height: 500px; overflow-y: auto;">
          <!-- ランク表示 -->
          <h6 class="card-subtitle mb-2 text-muted">Rank: {{ character.rank }}</h6>
          
          <!-- キャラクターの名前 -->
          <h5 class="card-title">{{ character.name }}</h5>

          <!-- ヒーローかヴィランかで表示内容を変更 -->
          <p v-if="showDetails && character.heroName !== '-'" class="card-text">
            <strong>{{ character.heroName ? 'ヒーロー名' : 'ヴィラン名' }}:</strong>
            {{ character.heroName || character.villainName }}
          </p>

          <!-- 詳細情報、showDetailsがtrueの場合のみ表示 -->
          <p v-if="showDetails && character.ability !== '-' " class="card-text"><strong>能力:</strong> {{ character.ability }}</p>
          <p v-if="showDetails && character.birthday !== '-' " class="card-text"><strong>誕生日:</strong> {{ character.birthday }}</p>
          <p v-if="showDetails && character.school !== '-' " class="card-text"><strong>学校:</strong> {{ character.school }}</p>
          <p v-if="showDetails && character.formerSchool !== '-' " class="card-text"><strong>前の学校:</strong> {{ character.formerSchool }}</p>
          <p v-if="showDetails && character.height !== '-' " class="card-text"><strong>身長:</strong> {{ character.height }}</p>
          <p v-if="showDetails && character.bloodType !== '-' " class="card-text"><strong>血液型:</strong> {{ character.bloodType }}</p>
          <p v-if="showDetails && character.likes !== '-' " class="card-text"><strong>好きなもの:</strong> {{ character.likes }}</p>
          <p v-if="showDetails && character.personality !== '-' " class="card-text"><strong>性格:</strong> {{ character.personality }}</p>
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
