<template>


      <nav>
        <RouterLink to="/">Home</RouterLink>
        <RouterLink to="/about">About</RouterLink>
      </nav>


  <RouterView />
</template>

<script setup>
import { RouterLink, RouterView } from 'vue-router'
import navbar from './components/NavBar.vue'
</script>

