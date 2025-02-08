<template>
  <div class="card mb-4" style="max-width: 540px; margin: 0 auto; border-radius: 20px; background-color: #f7f7f7; border: 2px solid #dcdcdc;">
    <div class="row g-0">
      <!-- キャラクター画像 -->
      <div class="col-12" @click="showProfile" style="border-radius: 20px 20px 0 0; overflow: hidden;">
        <img 
          :src="getImageUrl(character.image)" 
          :alt="character.name" 
          class="img-fluid rounded-start"
          :class="{'zoom-effect': showZoomEffect}"
          @mouseover="onMouseOver"
          @mouseleave="onMouseLeave"
          style="object-fit: cover; height: 200px; width: 100%;" 
        />
      </div>

      <div class="col-12">
        <div class="card-body" style="padding: 20px; max-height: 500px; overflow-y: auto;">
          <!-- ランキング表示 -->
          <div class="d-flex justify-content-between align-items-center mb-3">
            <h6 class="card-subtitle text-muted" style="font-size: 1.2rem;">Rank:</h6>
            <!-- ランクバッジ -->
            <div :class="['badge', getRankClass(character.rank), 'fs-4', 'fw-bold', 'px-4', 'py-2', 'rounded-pill', 'text-light', 'shadow-lg', 'border-0']">
              {{ character.rank }}
            </div>
          </div>
          
          <!-- キャラクターの名前 -->
          <h5 class="card-title" style="font-size: 1.4rem; font-weight: bold;">{{ character.name }}</h5>

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

// ズームエフェクトを管理する状態
const showZoomEffect = ref(false);

// マウスが画像に入った時の処理
const onMouseOver = () => {
  showZoomEffect.value = true;
};

// マウスが画像から離れた時の処理
const onMouseLeave = () => {
  showZoomEffect.value = false;
};

// ランクのクラスを動的に設定
const getRankClass = (rank) => {
  if (rank === '1') return 'bg-warning text-dark border-warning';  // ゴールド
  if (rank === '2') return 'bg-secondary text-dark border-secondary';  // シルバー
  if (rank === '3') return 'bg-bronze text-dark border-bronze';  // ブロンズ
  return 'bg-primary text-white';  // その他
};
</script>

<style scoped>
.zoom-effect {
  transform: scale(1.1);  /* 画像を10%拡大 */
  transition: transform 0.3s ease-in-out; /* 画像のズームにスムーズな遷移 */
}

/* ブロンズの色をカスタマイズ */
.bg-bronze {
  background-color: #cd7f32 !important;
  border-color: #cd7f32 !important;
}

/* ゴールドの色をカスタマイズ */
.bg-warning {
  background-color: #ffd700 !important;
  border-color: #ffd700 !important;
}

/* シルバーの色をカスタマイズ */
.bg-secondary {
  background-color: #c0c0c0 !important;
  border-color: #c0c0c0 !important;
}
</style>
