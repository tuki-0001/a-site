<template>
  <div class="card mb-4" style="max-width: 540px; margin: 0 auto; border-radius: 20px; background-color: #f7f7f7; border: 2px solid #dcdcdc; box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);">
    <div class="row g-0">
      <!-- キャラクター画像 -->
      <div class="col-12" @click="showProfile" style="border-radius: 20px 20px 0 0; overflow: hidden;">
        <!-- 画像を角丸に変更 -->
        <img 
          :src="getImageUrl(character.image)" 
          :alt="character.name" 
          class="img-fluid zoom-effect"
          style="object-fit: cover; height: 200px; width: 100%; border-radius: 10px;" 
        />
      </div>

      <div class="col-12">
        <div class="card-body" style="padding: 20px; max-height: 500px; overflow-y: auto;">
          <!-- ランキング表示 -->
          <div class="d-flex justify-content-between align-items-center mb-3">
            <h6 class="card-subtitle text-muted" style="font-size: 1.2rem;">Rank:</h6>
            <div :class="['badge', getRankClass(character.rank)]" style="font-size: 1.5rem; font-weight: bold; padding: 10px 20px; border-radius: 12px;">
              {{ character.rank }}
            </div>
          </div>
          
          <!-- キャラクターの名前 -->
          <h5 :class="getNameClass(character.rank)" class="card-title" style="font-size: 1.4rem; font-weight: bold;">
            {{ character.name }}
          </h5>

          <!-- ヒーローかヴィランかで表示内容を変更 -->
          <p v-if="showDetails && character.heroName !== '-'" class="card-text" style="font-size: 1.1rem;">
            <strong>{{ character.heroName ? 'ヒーロー名' : 'ヴィラン名' }}:</strong>
            {{ character.heroName || character.villainName }}
          </p>

          <!-- 詳細情報、showDetailsがtrueの場合のみ表示 -->
          <p v-if="showDetails && character.ability !== '-' " class="card-text" style="font-size: 1.1rem;"><strong>能力:</strong> {{ character.ability }}</p>
          <p v-if="showDetails && character.birthday !== '-' " class="card-text" style="font-size: 1.1rem;"><strong>誕生日:</strong> {{ character.birthday }}</p>
          <p v-if="showDetails && character.school !== '-' " class="card-text" style="font-size: 1.1rem;"><strong>学校:</strong> {{ character.school }}</p>
          <p v-if="showDetails && character.formerSchool !== '-' " class="card-text" style="font-size: 1.1rem;"><strong>前の学校:</strong> {{ character.formerSchool }}</p>
          <p v-if="showDetails && character.height !== '-' " class="card-text" style="font-size: 1.1rem;"><strong>身長:</strong> {{ character.height }}</p>
          <p v-if="showDetails && character.bloodType !== '-' " class="card-text" style="font-size: 1.1rem;"><strong>血液型:</strong> {{ character.bloodType }}</p>
          <p v-if="showDetails && character.likes !== '-' " class="card-text" style="font-size: 1.1rem;"><strong>好きなもの:</strong> {{ character.likes }}</p>
          <p v-if="showDetails && character.personality !== '-' " class="card-text" style="font-size: 1.1rem;"><strong>性格:</strong> {{ character.personality }}</p>

          <!-- 詳細ボタン -->
          <button 
            @click="showProfile"
            class="btn btn-info w-100 mt-3"
            style="font-size: 1.2rem; padding: 10px 0; border-radius: 10px; transition: background-color 0.3s;"
          >
            {{ showDetails ? '閉じる' : '詳細を見る' }}
          </button>
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

// ランキングに応じたスタイルクラスを返す
const getRankClass = (rank) => {
  switch (rank) {
    case '1':
      return 'bg-warning text-dark'; // ゴールド
    case '2':
      return 'bg-secondary text-white'; // シルバー
    case '3':
      return 'bg-bronze text-white'; // ブロンズ
    default:
      return 'bg-primary text-white'; // その他は青
  }
};

// ランキングに応じた名前の色を返す
const getNameClass = (rank) => {
  switch (rank) {
    case '1':
      return 'text-warning'; // ゴールド
    case '2':
      return 'text-secondary'; // シルバー
    case '3':
      return 'text-bronze'; // ブロンズ
    default:
      return 'text-primary'; // その他
  }
};
</script>

<style scoped>
/* Bootstrapのみで画像ズームエフェクト */
.zoom-effect {
  transition: transform 0.3s ease-in-out;
}

.zoom-effect:hover {
  transform: scale(1.1);  /* ホバー時に画像を10%拡大 */
}

</style>
