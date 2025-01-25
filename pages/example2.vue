<script setup>
const characters = [
  {
    rank: 8,
    name: "荼毘",
    aliasType: "ヴィラン名", // ヴィランの場合
    alias: "荼毘",
    ability: "蒼炎",
    birthday: "1月18日",
    height: "176cm",
    bloodType: "不明",
    likes: "蕎麦",
    personality: "つかめない",
    image: "https://via.placeholder.com/120", // 仮画像
  },
  {
    rank: 1,
    name: "爆豪勝己",
    aliasType: "ヒーロー名", // ヒーローの場合
    alias: "大・爆・殺・神ダイナマイト",
    ability: "爆破",
    birthday: "4月20日",
    height: "172cm",
    bloodType: "A型",
    likes: "辛い食べ物全般、登山",
    personality: "暴言自信家",
    image: "https://via.placeholder.com/120", // 仮画像
  },
];
</script>

<template>
  <div class="container mt-5">
    <div class="row">
      <!-- 各キャラクターカードをループで表示 -->
      <div v-for="character in characters" :key="character.rank" class="col-12 col-md-6 col-lg-4 mb-4">
        <div class="license-card mx-auto p-3 shadow">
          <!-- ヘッダー部分 -->
          <div class="license-header text-center mb-3">
            <h2 class="h5 mb-0">{{ character.rank }}位 {{ character.name }}</h2>
          </div>
          <!-- メイン部分 -->
          <div class="d-flex align-items-start">
            <img
              :src="character.image"
              alt="キャラクター画像"
              class="character-image"
            />
            <div class="ms-3">
              <table class="table table-sm mb-0">
                <tbody>
                  <!-- ヒーロー名またはヴィラン名を表示 -->
                  <tr>
                    <th>{{ character.aliasType }}</th>
                    <td>{{ character.alias }}</td>
                  </tr>
                  <tr>
                    <th>個性</th>
                    <td>{{ character.ability }}</td>
                  </tr>
                  <tr>
                    <th>誕生日</th>
                    <td>{{ character.birthday }}</td>
                  </tr>
                  <tr>
                    <th>身長</th>
                    <td>{{ character.height }}</td>
                  </tr>
                  <tr v-if="character.bloodType">
                    <th>血液型</th>
                    <td>{{ character.bloodType }}</td>
                  </tr>
                  <tr>
                    <th>好きなもの</th>
                    <td>{{ character.likes }}</td>
                  </tr>
                  <tr>
                    <th>性格</th>
                    <td>{{ character.personality }}</td>
                  </tr>
                </tbody>
              </table>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<style>
/* 全体の背景 */
body {
  background-color: #f7f7f7;
}

/* 免許証カード */
.license-card {
  max-width: 500px;
  border: 2px solid #000;
  border-radius: 8px;
  background-color: #fff;
}

.license-header {
  background-color: #007bff;
  color: white;
  padding: 10px;
  border-radius: 4px;
}

/* キャラクター画像 */
.character-image {
  width: 120px;
  height: 120px;
  border-radius: 8px;
  border: 2px solid #ccc;
  object-fit: cover;
}
</style>
