<template>
  <div class="card mb-4" style="max-width: 540px;">
    <div class="row g-0">
      <!-- キャラクター画像 -->
      <div class="col-6 col-md-6" @click="toggleDetails">
        <img 
          :src="getImageUrl(character.image)" 
          :alt="character.name" 
          class="img-fluid rounded-start"
        />
      </div>

      <div class="col-6 col-md-6">
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
          <p v-if="showDetails && character.ability !== '-' " class="card-text">
            <strong>能力:</strong> {{ character.ability }}
          </p>
          <p v-if="showDetails && character.birthday !== '-' " class="card-text">
            <strong>誕生日:</strong> {{ character.birthday }}
          </p>
          <p v-if="showDetails && character.school !== '-' " class="card-text">
            <strong>学校:</strong> {{ character.school }}
          </p>
          <p v-if="showDetails && character.formerSchool !== '-' " class="card-text">
            <strong>前の学校:</strong> {{ character.formerSchool }}
          </p>
          <p v-if="showDetails && character.height !== '-' " class="card-text">
            <strong>身長:</strong> {{ character.height }}
          </p>
          <p v-if="showDetails && character.bloodType !== '-' " class="card-text">
            <strong>血液型:</strong> {{ character.bloodType }}
          </p>
          <p v-if="showDetails && character.likes !== '-' " class="card-text">
            <strong>好きなもの:</strong> {{ character.likes }}
          </p>
          <p v-if="showDetails && character.personality !== '-' " class="card-text">
            <strong>性格:</strong> {{ character.personality }}
          </p>

          <!-- 詳細表示の切り替えボタン -->
          <button @click="toggleDetails" class="btn btn-primary mt-3">
            {{ showDetails ? '閉じる' : '詳細' }}
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

// 詳細情報表示の状態を管理
const showDetails = ref(false);

// 詳細情報の表示/非表示を切り替える
const toggleDetails = () => {
  showDetails.value = !showDetails.value;
};

// 画像パスを取得する関数
const getImageUrl = (image) => {
  return image || '/img/default-image.jpg'; // 画像がない場合はデフォルト画像
};
</script>
