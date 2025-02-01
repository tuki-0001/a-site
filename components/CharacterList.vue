<template>
  <div>
    <div v-for="character in sortedCharacters" :key="character.id" class="character-card">
      <img :src="`/img/${character.image}`" :alt="character.name" class="rounded-circle" style="width: 120px; height: 120px; object-fit: cover; margin-right: 20px;">
      <h3>{{ character.name }}</h3>
      <p><strong>Hero Name:</strong> {{ character.heroName }}</p>
      <p><strong>Ability:</strong> {{ character.ability }}</p>
      <p><strong>Birthday:</strong> {{ character.birthday }}</p>
    </div>
  </div>
</template>

<script>
export default {
  props: {
    sortedCharacters: Array, // 親コンポーネントからデータを受け取る
  }
};
</script>