<template>
  <div class="container mt-5">
    <div class="row">
      <div class="col-md-4 col-sm-6 mb-4" v-for="character in sortedCharacters" :key="character.rank">
        <CharacterCard :character="character" />
      </div>
    </div>
  </div>
</template>

<script setup>
import CharacterCard from '@/components/CharacterCard.vue';

defineProps({
  sortedCharacters: Array,
});
</script>
