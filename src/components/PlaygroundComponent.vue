<template>
  <div
    ref="elementToConvert"
    :style="playgroundGrid"
    class="playground__grid playground__style"
  >
    <div
      v-for="(item, index) in level * 5"
      :key="index"
      style="width: auto; height: auto; border: 1px solid black"
      class="circle__grid"
    >
      <CircleBrailleComponent
        v-for="(item, index) in 6"
        :key="index"
      ></CircleBrailleComponent>
    </div>
  </div>
  <q-btn
    class="q-mt-lg"
    rounded
    color="primary"
    label="Validar mi respuesta"
    @click="validateRound()"
  />
</template>

<script setup lang="ts">
import { Ref, reactive, ref } from 'vue';
import { useRoute } from 'vue-router';
import CircleBrailleComponent from './CircleBrailleComponent.vue';
import htmlToImage from 'html-to-image';

const route = useRoute();
const level: Ref<number> = ref(Number(route.params.level));
const elementToConvert = ref(null);


const playgroundGrid = reactive({
  display: 'grid',
  'grid-template-columns': 'repeat(5, 1fr)',
  'grid-template-rows': `repeat(${level.value}, 150px)`,
});
const rounds: Ref<number> = ref(5);
const current_round: Ref<number> = ref(1);
const validateRound = () => {
  if (current_round.value <= rounds.value) {
    alert('siga jugando');
    current_round.value++;
  } else {
    alert('El juego se acabao');
  }
};
</script>

<style scoped>
.playground__style {
  width: 350px;
  height: 450px;
  background-color: white;
}

.circle__grid {
  display: grid;
  grid-template-columns: repeat(2, 1fr);
  grid-template-rows: repeat(3, 1fr);
}
</style>
