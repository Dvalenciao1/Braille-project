<template>
  <span
    @click="greyColor = greyColor === '#1d1d1d' ? '#cfd8dc' : '#1d1d1d'"
    :style="{ 'background-color': greyColor }"
    class="circle__fill"
  ></span>
</template>
<script setup lang="ts">
import { Ref, ref } from 'vue';

const greyColor: Ref<string> = ref('#cfd8dc');
</script>

<style scoped>
.circle__fill {
  width: 25px;
  height: 25px;
  align-self: center;
  justify-self: center;
  border-radius: 50px;
}
</style>
