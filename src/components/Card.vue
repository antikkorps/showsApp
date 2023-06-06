<script setup>
import { defineProps } from 'vue';

const { id, name, status, image, origin, species } = defineProps([
  'id',
  'name',
  'status',
  'image',
  'origin',
  'species',
]);
</script>
<template>
  <n-card>
    <template #cover>
      <img :src="image" :alt="name" class="card-image" />
    </template>
    <h2 class="card-title">{{ name }}</h2>
    <p class="card-status">Status: {{ status }}</p>
    <p class="card-status">Origin of Character: {{ origin }}</p>
    <p class="card-status">Species: {{ species }}</p>
  </n-card>
</template>

<style scoped>
/* Card Styles */

.n-card {
  width: 200px;
  margin: 10px 20px;
  height: 400px;
}
.n-card img {
  height: 250px;
}

p {
  font-size: 10px;
}

.jobs {
  display: flex;
  flex-wrap: wrap;
}
</style>
