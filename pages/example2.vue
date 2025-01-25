<script setup>
const characters = [
  {
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
    image: "https://via.placeholder.com/120", // キャラ画像
  },
  {
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
    image: "https://via.placeholder.com/120", // キャラ画像
  },
  {
    name: "轟焦凍",
    heroName: "ショート",
    ability: "半冷半熱",
    school: "雄英高校ヒーロー科1年A組",
    formerSchool: "凝山中学校",
    birthday: "1月11日",
    height: "176cm",
    bloodType: "O型",
    likes: "蕎麦（温かくないやつ）",
    personality: "クール＆ホットな天然",
    image: "https://via.placeholder.com/120", // キャラ画像
  },
  {
    name: "相澤消太",
    heroName: "抹消ヒーローイレイザーヘッド",
    ability: "抹消",
    school: "ー",
    formerSchool: "ー",
    birthday: "11月8日",
    height: "183cm",
    bloodType: "B型",
    likes: "ねこ",
    personality: "なんだかんだあまい",
    image: "https://via.placeholder.com/120", // キャラ画像
  },
  {
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
    image: "https://via.placeholder.com/120", // キャラ画像
  },
  {
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
    image: "https://via.placeholder.com/120", // キャラ画像
  },
  {
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
    image: "https://via.placeholder.com/120", // キャラ画像
  },
  {
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
    image: "https://via.placeholder.com/120", // キャラ画像
  },
  {
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
    image: "https://via.placeholder.com/120", // キャラ画像
  },
  {
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
    image: "https://via.placeholder.com/120", // キャラ画像
  },
  {
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
    image: "https://via.placeholder.com/120", // キャラ画像
  },
  {
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
    image: "https://via.placeholder.com/120", // キャラ画像
  },
  {
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
    image: "https://via.placeholder.com/120", // キャラ画像
  },
  {
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
    image: "https://via.placeholder.com/120", // キャラ画像
  },
  {
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
    image: "https://via.placeholder.com/120", // キャラ画像
  },
  {
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
    image: "https://via.placeholder.com/120", // キャラ画像
  },
  {
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
    image: "https://via.placeholder.com/120", // キャラ画像
  },
  {
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
    image: "https://via.placeholder.com/120", // キャラ画像
  },
  {
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
    image: "https://via.placeholder.com/120", // キャラ画像
  },
  {
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
    image: "https://via.placeholder.com/120", // キャラ画像
  },
];
</script>

<template>
  <div class="container mt-5">
    <div class="row">
      <!-- 各キャラクターカードをループで表示 -->
      <div v-for="(character, index) in characters" :key="index" class="col-12 col-md-6 col-lg-4 mb-4">
        <div class="license-card mx-auto p-3 shadow">
          <!-- ヘッダー部分 -->
          <div class="license-header text-center mb-3">
            <h2 class="h5 mb-0">{{ index + 1 }}位 {{ character.name }}</h2>
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
                  <tr>
                    <th>ヒーロー名</th>
                    <td>{{ character.heroName }}</td>
                  </tr>
                  <tr>
                    <th>個性</th>
                    <td>{{ character.ability }}</td>
                  </tr>
                  <tr>
                    <th>学科</th>
                    <td>{{ character.school }}</td>
                  </tr>
                  <tr>
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
                  <tr>
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