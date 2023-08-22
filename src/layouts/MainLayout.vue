<template>
  <q-layout view="hHh LpR fFf">
    <q-header elevated style="height: 70px; background-color: #F69E53;">
      <q-toolbar class="q-pa-lg">
        <q-toolbar-title>Braille Play</q-toolbar-title>
      </q-toolbar>
    </q-header>

    <q-page-container>
      <router-view />
    </q-page-container>
  </q-layout>
</template>

<script setup lang="ts"></script>
