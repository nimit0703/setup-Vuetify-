<template>
  <v-container class="fill-height">
    <button @click="toggleTheme">theme</button>
  </v-container>
</template>

<script setup lang="ts">
//
import { useTheme } from 'vuetify'

const theme = useTheme()

function toggleTheme() {
  theme.global.name.value = theme.global.current.value.dark ? 'light' : 'dark'
}
</script>
