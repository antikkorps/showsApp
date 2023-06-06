<script setup>
import RickAndMorty from './components/RickAndMortyView.vue';
import Hero from './components/Hero.vue';
import PracticeSlot from './components/PracticeSlot.vue';
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
    <PracticeSlot>
      <h1>Slot</h1>
      <template #header> <h2>This is the slot Header</h2> </template
      ><template #footer> <h2>This is the slot Footer</h2> </template>
    </PracticeSlot>
  </main>
</template>

<style scoped></style>
