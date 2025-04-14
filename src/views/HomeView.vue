<script setup lang="ts">
import TheWelcome from '../components/TheWelcome.vue'
import InputText from 'primevue/inputtext';

import { ref } from 'vue';

const text = ref('')
</script>

<template>
  <main>
    <div class="home">
      <h1>Welcome to Your Vue.js App</h1>
      <InputText v-model="text" placeholder="Enter text" />
    </div>
  </main>
</template>
