<script setup>
import { defineProps } from 'vue';

const { image, name, occupation, status } = defineProps([
  'image',
  'name',
  'occupation',
  'status',
]);
</script>
<template>
  <n-card title="Card with Cover">
    <template #cover>
      <img :src="results.image" :alt="results.name" class="card-image" />
    </template>
    <h3 class="card-title">{{ results.name }}</h3>
    <p class="card-status">{{ results.status }}</p>
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
