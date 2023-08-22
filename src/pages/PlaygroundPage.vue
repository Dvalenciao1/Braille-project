<template>
  <q-page padding style="background-color: #ffe0b2">
    <div class="row justify-center q-py-md">
      <span class="text-h6 col-3">Puntaje</span>
      <span class="text-h6 text-weight-regular">100 Puntos</span>
    </div>
    <div class="column items-center">
      <PlaygroundComponent></PlaygroundComponent>
    </div>
  </q-page>
</template>

<script setup lang="ts">
import PlaygroundComponent from 'src/components/PlaygroundComponent.vue';
</script>
