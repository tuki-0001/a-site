<script setup>
const characters = [
  {
    rank: 1,
    name: "爆豪勝己",
    heroName: "大・爆・殺・神ダイナマイト",
    ability: "爆破",
    school: "雄英高校ヒーロー科1年A組",
    formerSchool: "折寺中学校",
    birthday: "4月20日",
    height: "172cm",
    bloodType: "A型",
    likes: "辛い食べ物全般、登山",
    personality: "暴言自信家",
    image: "https://via.placeholder.com/120",
  },
  {
    rank: 8,
    name: "荼毘",
    villainName: "荼毘",
    ability: "蒼炎",
    school: null,
    formerSchool: null,
    birthday: "1月18日",
    height: "176cm",
    bloodType: null,
    likes: "蕎麦",
    personality: "つかめない",
    image: "https://via.placeholder.com/120",
  },
  {
    rank: 2,
    name: "緑谷出久",
    heroName: "デク",
    ability: "ワン・フォー・オール",
    school: "雄英高校ヒーロー科1年A組",
    formerSchool: "折寺中学校",
    birthday: "7月15日",
    height: "166cm",
    bloodType: "O型",
    likes: "カツ丼、ヒーロー分析ノート",
    personality: "真面目で努力家",
    image: "https://via.placeholder.com/120",
  },
];

// 順位でソート
const sortedCharacters = characters.sort((a, b) => a.rank - b.rank);
</script>

<template>
  <div class="container mt-5">
    <div class="row">
      <!-- 順位順で表示 -->
      <div v-for="character in sortedCharacters" :key="character.rank" class="col-12 col-md-6 col-lg-4 mb-4">
        <div class="license-card mx-auto p-3 shadow">
          <!-- ヘッダー部分 -->
          <div class="license-header text-center mb-3">
            <h2 class="h5 mb-0">
              <!-- 順位表示 -->
              <span class="rank-circle">{{ character.rank }}</span> {{ character.name }}
            </h2>
          </div>
          <!-- メイン部分 -->
          <div class="d-flex align-items-start">
            <!-- 画像 -->
            <div class="character-image-wrapper">
              <img
                :src="character.image"
                alt="キャラクター画像"
                class="character-image"
              />
            </div>
            <div class="ms-3">
              <table class="table table-sm mb-0">
                <tbody>
                  <tr v-if="character.heroName">
                    <th>ヒーロー名</th>
                    <td>{{ character.heroName }}</td>
                  </tr>
                  <tr v-if="character.villainName">
                    <th>ヴィラン名</th>
                    <td>{{ character.villainName }}</td>
                  </tr>
                  <tr>
                    <th>個性</th>
                    <td>{{ character.ability }}</td>
                  </tr>
                  <tr v-if="character.school">
                    <th>学科</th>
                    <td>{{ character.school }}</td>
                  </tr>
                  <tr v-if="character.formerSchool">
                    <th>出身校</th>
                    <td>{{ character.formerSchool }}</td>
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
/* 既存のスタイルと同じ */
body {
  background-color: #f7f7f7;
}

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

.rank-circle {
  display: inline-block;
  width: 30px;
  height: 30px;
  background-color: gold;
  color: black;
  font-weight: bold;
  border-radius: 50%;
  text-align: center;
  line-height: 30px;
  margin-right: 10px;
}

.character-image-wrapper {
  flex-shrink: 0;
  width: 120px;
  height: 120px;
  border-radius: 8px;
  border: 2px solid #007bff;
  overflow: hidden;
}

.character-image {
  width: 100%;
  height: 100%;
  object-fit: cover;
}
</style>
