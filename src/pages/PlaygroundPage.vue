<template>
  <q-page padding style="background-color: #ffe0b2">
    <div class="row justify-center">
      <div class="title__grid col-12 col-md-4 q-pa-md">
        <span class="text-h6 col-3">Puntaje:</span>
        <span class="text-h6 text-weight-regular text-right">
          {{ score }} Puntos
        </span>
        <p class="text-h6 word__grid">
          Palabras: <span class="text-h6 text-weight-regular">{{ words }}</span>
        </p>
      </div>
    </div>
    <div class="column items-center">
      <PlaygroundComponent></PlaygroundComponent>
    </div>
  </q-page>
</template>

<script setup lang="ts">
import axios from 'axios';
import PlaygroundComponent from 'src/components/PlaygroundComponent.vue';
import { Ref, ref } from 'vue';
import { useRoute } from 'vue-router';
const route = useRoute();
const level: Ref<number> = ref(Number(route.params.level));
const score: Ref<number> = ref(50);
const listWord: Ref<string[]> = ref([]);
const words: Ref<string> = ref('');

axios
  .get('https://clientes.api.greenborn.com.ar/public-random-word?c=10&l=5')
  .then((res) => {
    res.data.forEach((element: string) => {
      if (element.length === 5 && listWord.value.length < level.value) {
        listWord.value.push(element);
      }
    });

    words.value = listWord.value.join();
  });
</script>

<style scoped>
.title__grid {
  display: grid;
  grid-template-columns: repeat(2, 1fr);
  grid-template-rows: 30px 30px;
  gap: 7px 0px;
}

.word__grid {
  grid-column: 1 / 3;
}
</style>
