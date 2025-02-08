<template>
  <div class="card mb-4" style="max-width: 540px;" v-for="(character, index) in characters" :key="index">
    <div class="row g-0">
      <!-- キャラクター画像 -->
      <div class="col-6 col-md-6" @click="toggleDetails(index)">
        <img 
          :src="getImageUrl(character.image)" 
          :alt="character.name" 
          class="img-fluid rounded-start" 
          style="object-fit: cover; height: 120px; width: 100%;" 
        />
      </div>

      <div class="col-6 col-md-6">
        <div class="card-body">
          <!-- ランク表示 -->
          <h6 class="card-subtitle mb-2 text-muted">Rank: {{ character.rank }}</h6>
          
          <!-- キャラクターの名前 -->
          <h5 class="card-title">{{ character.name }}</h5>

          <!-- ヒーローかヴィランかで表示内容を変更 -->
          <p v-if="showDetails[index] && character.heroName !== '-'" class="card-text">
           <strong>{{ character.heroName ? 'ヒーロー名' : 'ヴィラン名' }}:</strong>
            {{ character.heroName || character.villainName }}
          </p>

          <!-- 詳細情報、showDetailsがtrueの場合のみ表示 -->
          <p v-if="showDetails[index] && character.ability !== '-' " class="card-text"><strong>能力:</strong> {{ character.ability }}</p>
          <p v-if="showDetails[index] && character.birthday !== '-' " class="card-text"><strong>誕生日:</strong> {{ character.birthday }}</p>
          <p v-if="showDetails[index] && character.school !== '-' " class="card-text"><strong>学校:</strong> {{ character.school }}</p>
          <p v-if="showDetails[index] && character.formerSchool !== '-' " class="card-text"><strong>前の学校:</strong> {{ character.formerSchool }}</p>
          <p v-if="showDetails[index] && character.height !== '-' " class="card-text"><strong>身長:</strong> {{ character.height }}</p>
          <p v-if="showDetails[index] && character.bloodType !== '-' " class="card-text"><strong>血液型:</strong> {{ character.bloodType }}</p>
          <p v-if="showDetails[index] && character.likes !== '-' " class="card-text"><strong>好きなもの:</strong> {{ character.likes }}</p>
          <p v-if="showDetails[index] && character.personality !== '-' " class="card-text"><strong>性格:</strong> {{ character.personality }}</p>
        </div>
      </div>
    </div>
  </div>
</template>

<script setup>
import { ref } from 'vue';

// 親コンポーネントから渡される characters 配列を受け取る
const props = defineProps({
  characters: {
    type: Array,
    required: true,
  },
});

// 各キャラクターの詳細情報を表示するための状態を配列で管理
const showDetails = ref(Array(props.characters.length).fill(false));

// 画像クリックでプロフィール情報を表示
const toggleDetails = (index) => {
  // クリックされたカードの詳細情報をトグル
  showDetails.value[index] = !showDetails.value[index];
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
