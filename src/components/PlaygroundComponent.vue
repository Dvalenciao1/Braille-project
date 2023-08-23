<template>
  <div
    id="my-node"
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
  <div id="exponer"></div>
  <q-btn
    class="q-mt-lg"
    rounded
    color="primary"
    label="Validar mi respuesta"
    @click="validateRound()"
  />
</template>

<script setup>
import { reactive, ref } from 'vue';
import { useRoute } from 'vue-router';
import CircleBrailleComponent from './CircleBrailleComponent.vue';

import domtoimage from 'dom-to-image-more';

let img = new Image();
const convert = () => {
  domtoimage
    .toPng(document.getElementById('my-node'))
    .then(function (dataUrl) {
      img.src = dataUrl;
      var link = document.createElement('a');
      link.download = 'my-image-name.jpeg';
      link.href = dataUrl;
      link.click();
      //img.src contiene la imagen que necesitas
    })
    .catch(function (error) {
      console.error('oops, something went wrong!', error);
    });
};

const route = useRoute();
const level = ref(Number(route.params.level));

const playgroundGrid = reactive({
  display: 'grid',
  'grid-template-columns': 'repeat(5, 1fr)',
  'grid-template-rows': `repeat(${level.value}, 150px)`,
});
const rounds = ref(5);
const current_round = ref(1);
const validateRound = () => {
  if (current_round.value <= rounds.value) {
    convert();
    current_round.value++;
    //img contiene la imagen
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
