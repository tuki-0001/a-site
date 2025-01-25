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
    image:require('@/pages/img./ばくごう.jpg'),
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
  {
    rank: 12,
    name: "八木俊典",
    heroName: "オールマイト",
    ability: "ワン・フォー・オール",
    school: null,
    formerSchool:null,
    birthday: "6月10日",
    height: "220cm",
    bloodType: "A型",
    likes: "屋久杉・映画",
    personality: "意外とお茶目",
    image: "https://via.placeholder.com/120",
  },
  {
    rank: 13,
    name: "渡我被身子",
    villainName: "トガヒミコ",
    ability: "変身",
    school: null,
    formerSchool: null,
    birthday: "8月7日",
    height: "157cm",
    bloodType: null,
    likes: "血、柘榴",
    personality: "惚れっぽい",
    image: "https://via.placeholder.com/120",
  }, 
  {
    rank: 14,
    name: "上鳴電気",
    heroName: "スタンガンヒーローチャージズマ",
    ability: "帯電",
    school: "雄英高校ヒーロー科1年A組",
    formerSchool: "谷便第一中学校",
    birthday: "6月29日",
    height: "168㎝",
    bloodType: "O型",
    likes: "流行ってるもの、ハンバーガー",
    personality: "チャラい系男子",
    image: "https://via.placeholder.com/120",
  },
  {
    rank: 15,
    name: "心操人使",
    heroName: null,
    ability: "洗脳",
    school: "雄英高校普通科1年C組",
    formerSchool: "名部中学校",
    birthday: "7月1日",
    height: "177cm",
    bloodType: "AB型",
    likes: "猫 、サイクリング",
    personality: "ストイック",
    image: "https://via.placeholder.com/120",
  },
  {
    rank: 16,
    name: "天喰環",
    heroName: "サンイーター",
    ability: "再現",
    school: "雄英高校ヒーロー科3年A組",
    formerSchool: null,
    birthday: "3月4日",
    height: "177cm",
    bloodType: "AB型",
    likes: "蝶",
    personality: "ネガティブ能力マン",
    image: "https://via.placeholder.com/120",
  },
  {
    rank: 17,
    name: "ロディ・ソウル",
    heroName: null,
    ability: "魂",
    school: null,
    formerSchool: null,
    birthday: "2月13日",
    height: "174cm",
    bloodType: null,
    likes: null,
    personality:"お調子者",
    image: "https://via.placeholder.com/120",
  },
  {
    rank: 18,
    name: "飯田天哉",
    heroName: "インゲニウム",
    ability: "エンジン",
    school: "雄英高校ヒーロー科1年A組",
    formerSchool: "聡明中学校",
    birthday: "8月22日",
    height: "179cm",
    bloodType: "A型",
    likes: "勉強、ビーフシチュー",
    personality: "委員長気質",
    image: "https://via.placeholder.com/120",
  },
  {
    rank: 19,
    name: "常闇踏陰",
    heroName: "漆黒ヒーローツクヨミ",
    ability: "黒影",
    school: "雄英高校ヒーロー科1年A組",
    formerSchool: "円扉中学校",
    birthday: "10月30日",
    height: "158㎝",
    bloodType: "AB型",
    likes: "リンゴ、薄暗い所",
    personality: "深淵を好むクール系",
    image: "https://via.placeholder.com/120",
  },
  {
    rank: 20,
    name: "耳郎響香",
    heroName: "ヒアヒーローイヤホン=ジャック",
    ability: "イヤホンジャック",
    school: "雄英高校ヒーロー科1年A組",
    formerSchool: "辺須瓶中学校",
    birthday: "8月1日",
    height: "154cm",
    bloodType: "A型",
    likes: "ロック",
    personality: "恥ずかしがり屋",
    image: "https://via.placeholder.com/120",
  },
  {
    rank: 21,
    name: "通形ミリオ",
    heroName: "ルミリオン",
    ability: "透過",
    school: "雄英高校ヒーロー科3年B組",
    formerSchool: null,
    birthday: "7月15日",
    height: "181cm",
    bloodType: "O型",
    likes: "ラーメン、お笑い",
    personality: "太陽的存在",
    image: "https://via.placeholder.com/120",
  },
  {
    rank: 22,
    name: "八百万百",
    heroName: "万物ヒーロークリエティ",
    ability: "創造",
    school: "雄英高校ヒーロー科1年A組",
    formerSchool:"掘須磨大付属中学校",
    birthday: "9月23日",
    height: "173cm",
    bloodType: "A型",
    likes: "読書（図鑑などを好む）",
    personality: "たまにポンコツ",
    image: "https://via.placeholder.com/120",
  },
  {
    rank: 23,
    name: "兎山ルミ",
    heroName: "ラビットヒーローミルコ",
    ability: "兎",
    school: null,
    formerSchool: null,
    birthday: "3月1日",
    height: "159cm",
    bloodType: "O型",
    likes: "にんじん",
    personality: "男勝り",
    image: "https://via.placeholder.com/120",
  },
  {
    rank: 24,
    name: "瀬呂範太",
    heroName: "テーピンヒーローセロファン",
    ability: "テープ",
    school: "雄英高校ヒーロー科1年A組",
    formerSchool:"猿架舞中学校",
    birthday: "7月28日",
    height: "177cm",
    bloodType: "B型",
    likes: "健康に良い食べ物",
    personality: "空気読めるマン",
    image: "https://via.placeholder.com/120",
  },
  {
    rank: 25,
    name: "山田ひざし",
    heroName: "ボイスヒーロープレゼント・マイク",
    ability: "ヴォイス",
    school: null,
    formerSchool: null,
    birthday: "7月7日",
    height: "185cm",
    bloodType: "B型",
    likes: "ラジオ、TV",
    personality: "ハイテンション",
    image: "https://via.placeholder.com/120",
  },
  {
    rank: 26,
    name: "蛙吹梅雨",
    heroName: "梅雨入りヒーローFROPPY",
    ability: "蛙",
    school: "雄英高校ヒーロー科1年A組",
    formerSchool:"塩ノ洲中学校",
    birthday: "2月12日",
    height: "150cm",
    bloodType: "B型",
    likes: "雨 、ゼリー",
    personality: "友達想いの冷静淑女",
    image: "https://via.placeholder.com/120",
  },
  {
    rank: 27,
    name: "青山優雅",
    heroName: "輝きヒーローCan't stop twinkling.",
    ability: "ネビルレーザー",
    school: "雄英高校ヒーロー科1年A組",
    formerSchool:"聖カミイノ中学校",
    birthday: "5月30日",
    height: "168cm",
    bloodType: "O型",
    likes: "己",
    personality: "ナルシストな自由人",
    image: "https://via.placeholder.com/120",
  },
  {
    rank: 28,
    name: "障子目蔵",
    heroName: "触手ヒーローテンタコル",
    ability: "複製腕",
    school: "雄英高校ヒーロー科1年A組",
    formerSchool:"歌葉雨中学校",
    birthday: "2月15日",
    height: "187cm",
    bloodType: "B型",
    likes: "たこ焼き、イカスミパスタ",
    personality: "寡黙な紳士",
    image: "https://via.placeholder.com/120",
  },
  {
    rank: 29,
    name: "波動ねじれ",
    heroName: "ネジレチャン",
    ability: "波動",
    school: "雄英高校ヒーロー科3年A組",
    formerSchool: null,
    birthday: "10月6日",
    height: "164cm",
    bloodType: "B型",
    likes: "ユリの花、ジャスミンティー",
    personality: "好奇心旺盛",
    image: "https://via.placeholder.com/120",
  },
  {
    rank: 30,
    name: "袴田維",
    heroName: "ファイバーヒーローベストジーニスト",
    ability: "ファイバーマスター",
    school: null,
    formerSchool: null,
    birthday: "10月5日",
    height: "190cm",
    bloodType: "AB型",
    likes: "狼",
    personality: "何事もビッチリ",
    image: "https://via.placeholder.com/120",
  },
  {
    rank: 31,
    name: "分倍河原仁",
    villainName: "トゥワイス",
    ability: "二倍",
    school: null,
    formerSchool: null,
    birthday: "5月10日",
    height: "178cm",
    bloodType:"O型",
    likes: "煙草",
    personality: "支離滅裂",
    image: "https://via.placeholder.com/120",
  },
  {
    rank: 32,
    name: "筒美火伊那",
    villainName: "レディ・ナガン",
    ability: "ライフル / エアウォーク",
    school: null,
    formerSchool: null,
    birthday: "10月10日",
    height: "171cm",
    bloodType: null,
    likes: "キレイなもの、かわいいもの",
    personality:"勝気で男勝り",
    image: "https://via.placeholder.com/120",
  },
  {
    rank: 33,
    name: "芦戸三奈",
    heroName: "pinky",
    ability: "酸",
    school:"雄英高校ヒーロー科1年A組",
    formerSchool:"結田付中学校",
    birthday: "7月30日",
    height: "159cm",
    bloodType: "AB型",
    likes: "ダンス、納豆、オクラ、恋バナ",
    personality: "元気100%",
    image: "https://via.placeholder.com/120",
  },
  {
    rank: 34,
    name: "灰廻航一",
    heroName: "ザ・スカイクロウラー",
    ability: "飛行",
    school: null,
    formerSchool: null,
    birthday: "2月22日",
    height: "172cm",
    bloodType:null,
    likes: "カレー",
    personality: "気弱で温厚",
    image: "https://via.placeholder.com/120",
  },
  {
    rank: 35,
    name: "尾白猿夫",
    heroName: "武闘ヒーローテイルマン",
    ability: "尻尾",
    school:"雄英高校ヒーロー科1年A組",
    formerSchool:"舞木戸中学校",
    birthday: "5月28日",
    height: "169cm",
    bloodType: "O型",
    likes: "武術",
    personality: "普通に努力家",
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
