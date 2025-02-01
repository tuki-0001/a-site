<template>
  <div class="container mt-5">
    <div class="row">
      <div class="col-12">
        <div v-if="characters.length > 0">
          <!-- Sorted characters -->
          <div v-for="character in sortedCharacters" :key="character.rank" class="card mb-3">
            <div class="card-body d-flex align-items-center">
              <!-- Character Image -->
              <img :src="character.image" :alt="character.name" class="rounded-circle" style="width: 120px; height: 120px; object-fit: cover; margin-right: 20px;">
              
              <!-- Character Details -->
              <div>
                <div class="d-flex align-items-center mb-2">
                  <!-- Rank Badge -->
                  <span class="badge bg-warning text-dark" style="font-size: 1.5rem; padding: 10px 20px;">{{ character.rank }}</span>
                  <h3 class="ms-2">{{ character.name }}</h3>
                </div>
                <p class="mb-1"><strong>Hero Name:</strong> {{ character.heroName }}</p>
                <p class="mb-1"><strong>Ability:</strong> {{ character.ability }}</p>
                <p class="mb-1"><strong>Birthday:</strong> {{ character.birthday }}</p>
              </div>
            </div>
          </div>
        </div>
        <!-- No characters available -->
        <div v-else>
          <p>No characters available to display.</p>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  props: {
    characters: {
      type: Array,
      required: true,
    },
  },
  computed: {
    sortedCharacters() {
      // ソートされたキャラクターリストを返す
      return this.characters.sort((a, b) => a.rank - b.rank);
    },
  },
};
</script>

<style scoped>
.card-body {
  display: flex;
  align-items: center;
}

.card-body img {
  margin-right: 20px;
}

.card-body h3 {
  margin: 0;
}

.card-body p {
  margin: 0.5rem 0;
}
</style>
