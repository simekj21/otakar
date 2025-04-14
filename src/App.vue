<template>
  <div class="layout">
    <!-- Menubar s customizací -->
    <Menubar :model="items" class="menubar">
      <template #start>
        <RouterLink to="/">
          <img src="@/assets/otakar_logo_02.png" alt="Logo" width="200" />
        </RouterLink>
      </template>
    </Menubar>

    <main class="content">
      <RouterView />
    </main>
  </div>
</template>

<script setup>
import { useRouter } from 'vue-router'
import { ref } from 'vue'
import Menubar from 'primevue/menubar'

const router = useRouter()

const items = ref([
  { label: 'Home', command: () => router.push('/') },
  { label: 'About', command: () => router.push('/about') },
  { label: 'Services', command: () => router.push('/services') },
  { label: 'Contact', command: () => router.push('/contact') }
])
</script>

<style>
@import url('https://fonts.googleapis.com/css2?family=Inter:wght@400;500;600&display=swap');

.layout {
  display: flex;
  flex-direction: column;
  min-height: 100vh;
  font-family: 'Inter', sans-serif;
}

.content {
  padding-top: 80px;
  flex-grow: 1;
}

/* Menubar - fixní a stylované */
.menubar {
  position: fixed;
  top: 0;
  width: 100%;
  z-index: 1000;
  height: 70px;
  background-color: white;
  padding: 0 2rem;
  box-shadow: 0 2px 8px rgba(0, 0, 0, 0.05);
  display: flex;
  align-items: center;
  font-family: 'Inter', sans-serif;
  border-bottom: 1px solid #e0e0e0;
  padding: 0 2rem;
}

.p-menubar-item-link:hover {
  color: blue !important;
  background-color: white !important;
}

.p-menubar-item-content{
  transition: none !important;
}

.p-menubar {
  border: none !important;
  box-shadow: none !important;
  border-bottom: 1px solid #e0e0e0 !important;
}


</style>
