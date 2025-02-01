<template>
 <div class="container mt-5">
   <div class="row">
     <CharacterCard
       v-for="character in sortedCharacters"
       :key="character.rank"
       :character="character"
     />
   </div>
 </div>
</template>

<script>
import CharacterCard from '@/components/CharacterCard.vue';
export default {
 name: 'CharacterList',
 components: {
   CharacterCard,
 },
 props: {
   sortedCharacters: Array,
 },
}
</script>

