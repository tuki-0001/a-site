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
    name: "轟燈矢",
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
  {
    rank: 3,
    name: "轟焦凍",
    heroName: " ショート",
    ability: "半冷半熱",
    school: "雄英高校ヒーロー科1年A組",
    formerSchool: "凝山中学校",
    birthday: "1月11日",
    height: " 176cm",
    bloodType: "O型",
    likes: "蕎麦（温かくないやつ）",
    personality: "クール＆ホットな天然",
    image: "https://via.placeholder.com/120",
  },
  {
    rank: 4,
    name: "相澤消太",
    heroName: "抹消ヒーローイレイザーヘッド",
    ability: "抹消",
    school: null,
    formerSchool: null,
    birthday: "11月8日",
    height: "183cm",
    bloodType: "B型",
    likes: "ねこ",
    personality: "なんだかんだあまい",
    image: "https://via.placeholder.com/120",
  },
  {
    rank: 5,
    name: "切島鋭児郎",
    heroName: "剛健ヒーロー烈怒頼雄斗",
    ability: "硬化",
    school: "雄英高校ヒーロー科1年A組",
    formerSchool: "結田付中学校",
    birthday: "10月16日",
    height: "170cm<",
    bloodType: "O型",
    likes: "硬派な物、肉",
    personality: "快活ムードメーカー",
    image: "https://via.placeholder.com/120",
  },
  {
    rank: 6,
    name: "轟炎司",
    heroName: "フレイムヒーローエンデヴァー",
    ability: "ヘルフレイム",
    school: null,
    formerSchool: null,
    birthday: "8月8日",
    height: "195cm",
    bloodType: "AB型",
    likes: "葛餅",
    personality: "頑固オヤジ",
    image: "https://via.placeholder.com/120",
  },
  {
    rank: 7,
    name: "鷹見啓悟",
    heroName: "ウィングヒーローホークス",
    ability: "剛翼",
    school: null,
    formerSchool: null,
    birthday: "12月28日",
    height: "172cm",
    bloodType: "B型",
    likes: "鶏肉",
    personality: "目聡く耳聡い",
    image: "https://via.placeholder.com/120",
  },
  {
    rank: 9,
    name: "志村転弧",
    villainName: "死柄木弔",
    ability: "崩壊",
    school: null,
    formerSchool: null,
    birthday: "4月4日",
    height: "175cm",
    bloodType: null,
    likes: "ゲーム",
    personality: "子ども大人",
    image: "https://via.placeholder.com/120",
  },
  {
    rank: 10,
    name: "物間寧人",
    heroName: "ファントムシーフ",
    ability: "コピー",
    school: "雄英高校ヒーロー科1年B組",
    formerSchool: "逢沿中学校",
    birthday: "5月13日",
    height: "170cm",
    bloodType: "A型",
    likes: "フランス料理、バンド・デシネ",
    personality: "身内には優しい",
    image: "https://via.placeholder.com/120",
  },
  {
    rank: 11,
    name: "麗日お茶子",
    heroName: "ウラビティ",
    ability: "無重力",
    school: "雄英高校ヒーロー科1年A組",
    formerSchool: "露座柳中学校",
    birthday: "12月27日",
    height: "156cm",
    bloodType: "B型",
    likes: "星空、和食",
    personality: "いつも麗らか",
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
