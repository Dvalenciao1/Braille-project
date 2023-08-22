<template>
  <q-card flat class="my-card" style="background-color: #ffe0b2">
    <q-card-section>
      <q-img
        style="border-radius: 10px"
        :width="$q.screen.lt.md ? 100 + '%' : 500 + 'px'"
        height="400px"
        src="../img/init_image.jpeg"
        spinner-color="primary"
        spinner-size="82px"
      >
      </q-img>
    </q-card-section>
    <q-card-section class="colmn text-center">
      <span class="text-h4 text-weight-bold q-pt-md">BrailleTech</span>
      <p class="text-subtitle1 q-pt-sm" style="color: #57636c">
        Bienvenido! Te presento un juego<br />para aprender el lenguaje en
        Braille
      </p>
    </q-card-section>
    <q-card-section :class="{ row: true, 'justify-center': true }">
      <q-btn
        :style="{
          'background-color': '#5373c6',
          color: '#fff',
          height: $q.screen.lt.md ? 50 + 'px' : 'auto',
        }"
        class="col-12 col-md-6"
        label="Empezar"
        to="/init/level"
      />
    </q-card-section>
  </q-card>
</template>

<script setup lang="ts"></script>
