<template>
  <q-page class="row items-center justify-evenly">
    <div
      class="column absolute full-height q-py-md"
      :style="{
        width: $q.screen.gt.sm ? 1024 + 'px' : 100 + '%',
      }"
    >
      <q-card class="my-card col-12">
        <q-scroll-area style="width: auto; height: 800px">
          <q-card-section :horizontal="$q.screen.gt.md">
            <q-card-section class="col-12 col-md-6">
              <UploadPhotoComponent></UploadPhotoComponent>
            </q-card-section>
            <q-card-section class="col-12 col-md-6">
              <q-card-section>
                <q-input
                  v-model="text"
                  type="textarea"
                  label="Traducción"
                  outlined
                />
              </q-card-section>
              <q-card-section>
                <span class="text-h6 text-weight-regular q-pa-md ">Compartir</span>
                <q-card-actions align="evenly" class="q-my-md">
                  <q-btn color="positive" class="q-mt-sm" size="lg" icon="fa fa-envelope" />
                  <q-btn color="positive" class="q-mt-sm" size="lg" icon="fa-brands fa-facebook-f" />
                  <q-btn color="positive" class="q-mt-sm" size="lg" icon="fa-brands fa-whatsapp" />
                  <q-btn color="positive" class="q-mt-sm" size="lg" icon="fa-brands fa-twitter" />
                  <q-btn color="positive" class="q-mt-sm" size="lg" icon="fa-solid fa-clipboard" />
                </q-card-actions>
              </q-card-section>
            </q-card-section>
          </q-card-section>
        </q-scroll-area>
      </q-card>
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
