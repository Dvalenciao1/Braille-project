<template>
  <q-layout view="hHh LpR fFf">
    <q-header elevated style="height: 70px">
      <q-toolbar class="q-pa-lg">
        <q-toolbar-title> Traductor Braille</q-toolbar-title>
        <q-btn dense flat rounded color="bg-white" icon="fa-regular fa-heart" />
      </q-toolbar>
    </q-header>

    <q-page-container>
      <router-view />
    </q-page-container>
  </q-layout>
</template>

<script setup lang="ts"></script>
