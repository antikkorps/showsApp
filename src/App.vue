<script setup>
import RickAndMorty from './components/RickAndMortyView.vue';
import Hero from './components/Hero.vue';
</script>

<template>
  <main>
    <Hero />
    <Suspense>
      <template #default>
        <RickAndMorty />
      </template>
      <template #fallback>
        <div>
          <p>Loading ...</p>
        </div>
      </template>
    </Suspense>
  </main>
</template>

<style scoped></style>
