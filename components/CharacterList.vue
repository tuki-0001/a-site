<template>
  <div class="container mt-4">
    <div class="row">
      <!-- キャラクターカードを繰り返し表示 -->
      <div class="col-md-4" v-for="character in sortedCharacters" :key="character.rank">
        <CharacterCard :character="character" />
      </div>
    </div>
  </div>
</template>

<script setup>

// 親から渡されたキャラクターリストを受け取る
const props = defineProps({
  sortedCharacters: {
    type: Array,
    required: true,
  },
});
</script>
