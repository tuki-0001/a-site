<template>
 <div class="license-card mx-auto p-3 shadow">
   <div class="license-header text-center mb-3">
     <h2 class="h5 mb-0">
       <span class="rank-circle">{{ character.rank }}</span> {{ character.name }}
     </h2>
   </div>
   <div class="d-flex align-items-start">
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
</template>

<script>
export default {
 name: 'CharacterCard',
 props: {
   character: Object,
 },
}
</script>

<style scoped>
.license-card {
 /* スタイルの例 */
}
</style>
