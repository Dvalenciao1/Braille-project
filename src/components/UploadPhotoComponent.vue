<template>
  <q-card flat class="my-card">
    <q-card-section>
      <q-img
      class="fit"

        height="350px"
        src="https://placeimg.com/40/10/nature"
        spinner-color="primary"
        spinner-size="82px"
      >
        <template v-slot:error>
          <div class="absolute-full flex flex-center bg-negative text-white">
            Cannot load image
          </div>
        </template>
      </q-img>
    </q-card-section>
    <q-card-section>
      <q-btn class="fit" color="positive" label="capturar o subir imagen" />
    </q-card-section>
  </q-card>
</template>

<script setup lang="ts"></script>
