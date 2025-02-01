<template>
  <div class="character-list">
    <div v-for="character in sortedCharacters" :key="character.rank" class="character-item">
      <div class="d-flex p-3">
        <div class="character-image-wrapper">
          <img :src="character.image" :alt="character.name" class="character-image">
        </div>
        <div class="ms-3">
          <div class="d-flex align-items-center">
            <span class="rank-circle">{{ character.rank }}</span>
            <h3>{{ character.name }}</h3>
          </div>
          <p>Hero Name: {{ character.heroName }}</p>
          <p>Ability: {{ character.ability }}</p>
          <p>Birthday: {{ character.birthday }}</p>
        </div>
      </div>
    </div>
  </div>
</template>

<script setup>
props: {
  sortedCharacters: Array
}
</script>

<style scoped>
.character-item {
  border-bottom: 1px solid #ddd;
}

.character-image-wrapper {
  width: 120px;
  height: 120px;
  border-radius: 8px;
  overflow: hidden;
}

.character-image {
  width: 100%;
  height: 100%;
  object-fit: cover;
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
</style>
