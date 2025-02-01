<template>
  <div>
    <TitleWrapper :title="title" />
    <CharacterList :characters="sortedCharacters" />
  </div>
</template>

<script setup>
import { computed } from 'vue';
import TitleWrapper from '@/components/TitleWrapper.vue';
import CharacterList from '@/components/CharacterList.vue';

const title = 'Character Ranking';

const characters = [
  { name: 'All Might', rank: 1 },
  { name: 'Deku', rank: 2 },
  { name: 'Bakugo', rank: 3 },
  { name: 'Shigaraki', rank: 4 },
  { name: 'Todoroki', rank: 5 },
  { name: 'Endeavor', rank: 6 },
  { name: 'Hawks', rank: 7 },
  { name: 'Eraser Head', rank: 8 }
];

const sortedCharacters = computed(() => {
  return [...characters].sort((a, b) => a.rank - b.rank);
});
</script>
