<script setup>
import axios from 'axios';
import { ref, watch } from 'vue';
import Card from './Card.vue';

const names = ref([]);
const page = ref(1);

watch(page, async () => {
  await fetchCharacters();
});

async function fetchCharacters() {
  try {
    const response = await axios.get(
      `https://rickandmortyapi.com/api/character/?page=${page.value}`
    );
    names.value = response.data.results;
    console.log(response.data.results);
  } catch (error) {
    console.error(error);
  }
}

async function previousPage() {
  if (page.value > 1) {
    page.value--;
    await fetchCharacters();
  }
}

async function nextPage() {
  page.value++;
  await fetchCharacters();
}

fetchCharacters();
</script>

<template>
  <div class="container">
    <div class="cards">
      <Card
        v-for="name in names"
        :key="name.id"
        :name="name"
        :results="results"
      />
      <n-button type="primary">Primary</n-button>
    </div>
    <button @click="previousPage" :disabled="page === 1">Back</button>
    <button @click="nextPage">Next</button>
  </div>
</template>

<style scoped>
/* Breaking Bad Styles */

.container {
  background-color: rgb(27, 26, 26);
  padding: 30px;
}
.cards {
  max-width: 1000px;
  margin: 0 auto;
  display: flex;
  flex-wrap: wrap;
  height: 700px;
}
.cards h3 {
  font-weight: bold;
}
.cards p {
  font-size: 10px;
}
.jobs {
  display: flex;
  flex-wrap: wrap;
}
.button-container {
  display: flex;
  justify-content: center;
  padding-top: 30px;
}
.button-container button {
  border: none;
  width: 50px;
  height: 50px;
  border-radius: 100%;
  margin: 0 5px;
  cursor: pointer;
}
.spinner {
  display: flex;
  align-items: center;
  justify-content: center;
}
</style>
