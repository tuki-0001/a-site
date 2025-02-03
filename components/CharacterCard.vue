<template>
  <div class="container my-5">
    <div class="row row-cols-1 row-cols-md-2 row-cols-lg-3 g-4">
      <div class="col">
        <div class="license-card mx-auto p-4 shadow-lg rounded-3">
          <div class="license-header text-center mb-3">
            <h2 class="h5 mb-0">
              <span class="rank-circle">{{ character.rank }}</span> {{ character.name }}
            </h2>
          </div>
          <div class="d-flex align-items-start">
            <div class="character-image-wrapper text-center mb-3">
              <img :src="character.image || defaultImage" :alt="`${character.name}の画像`" class="img-fluid rounded-circle" style="width: 120px; height: 120px;" />
            </div>
            <div class="ms-3">
              <table class="table table-sm table-borderless mb-0">
                <tbody>
                  <tr v-if="character.heroName">
                    <th>ヒーロー名</th>
                    <td>{{ character.heroName }}</td>
                  </tr>
                  <tr v-if="character.villainName">
                    <th>ヴィラン名</th>
                    <td>{{ character.villainName }}</td>
                  </tr>
                  <tr v-if="character.ability">
                    <th>個性</th>
                    <td>{{ character.ability }}</td>
                  </tr>
                  <tr v-if="character.birthday">
                    <th>誕生日</th>
                    <td>{{ character.birthday }}</td>
                  </tr>
                  <tr v-if="character.height">
                    <th>身長</th>
                    <td>{{ character.height }}</td>
                  </tr>
                  <tr v-if="character.likes">
                    <th>好きなもの</th>
                    <td>{{ character.likes }}</td>
                  </tr>
                  <tr v-if="character.personality">
                    <th>性格</th>
                    <td>{{ character.personality }}</td>
                  </tr>
                </tbody>
              </table>
            </div>
          </div>
        </div>
      </div>
      <!-- 他のキャラクターカードも同様に追加 -->
      <div class="col">
        <div class="license-card mx-auto p-4 shadow-lg rounded-3">
          <!-- 2番目のキャラクターカードの内容もここに -->
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
    default: () => ({
      rank: "",
      name: "",
      heroName: "",
      villainName: "",
      ability: "",
      birthday: "",
      height: "",
      likes: "",
      personality: "",
      image: "",
    }),
  },
});

const defaultImage = '/img/default-image.jpg';
</script>
