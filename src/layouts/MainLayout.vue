<template>
  <q-layout view="lHh Lpr lFf">
    <q-header elevated class="bg-white q-px-md">
      <q-toolbar>
        <q-img src="logo/MINGJI (1).png" width="200px" />
        <q-space />
        <q-avatar size="60px">
          <img src="stickers/user.png" />
        </q-avatar>
      </q-toolbar>
    </q-header>

    <q-page-container>
      <router-view />
    </q-page-container>
  </q-layout>
</template>

<script setup>
import { ref } from "vue";
</script>
