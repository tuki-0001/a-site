<template>
  <div class="card mb-4" style="max-width: 540px;">
    <div class="row g-0">
      <!-- キャラクター画像 -->
      <div class="col-md-4">
        <img :src="getImageUrl(character.image)" :alt="character.name" class="img-fluid rounded-start" style="object-fit: cover; height: 120px;" />
      </div>
      <div class="col-md-8">
        <div class="card-body">
          <!-- キャラクターの名前 -->
          <h5 class="card-title">{{ character.name }}</h5>

          <!-- ヒーローかヴィランかで表示内容を変更 -->
          <p class="card-text">
            <strong>{{ character.heroName ? 'Hero Name' : 'Villain Name' }}:</strong>
            {{ character.heroName || character.villainName }}
          </p>

          <p class="card-text"><strong>能力:</strong> {{ character.ability }}</p>
<p class="card-text"><strong>誕生日:</strong> {{ character.birthday }}</p>
<p class="card-text"><strong>学校:</strong> {{ character.school }}</p>
<p class="card-text"><strong>前の学校:</strong> {{ character.formerSchool }}</p>
<p class="card-text"><strong>身長:</strong> {{ character.height }}</p>
<p class="card-text"><strong>血液型:</strong> {{ character.bloodType }}</p>
<p class="card-text"><strong>好きなもの:</strong> {{ character.likes }}</p>
<p class="card-text"><strong>性格:</strong> {{ character.personality }}</p>

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
  // 画像のパスが正しいかを再確認
  if (image) {
    // image が `img/` フォルダ内のパスならば、そのまま使います
    return image;
  } else {
    // デフォルト画像のパス
    return '/img/default-image.jpg';
  }
};
</script>
