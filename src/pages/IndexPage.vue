<template>
  <q-page style="background-color: #ffe0b2">
    <div class="column items-center q-pt-lg">
      <UploadPhotoComponent></UploadPhotoComponent>
    </div>
  </q-page>
</template>

<script setup lang="ts">
import UploadPhotoComponent from 'src/components/UploadPhotoComponent.vue';
</script>
<style scoped>
.q-textarea,
.q-field--labeled,
.q-field__native {
  min-height: 298px;
}
</style>
