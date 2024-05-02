<template>
  
  <Navbar />

  <RouterView />

</template>

<script>
import { RouterLink, RouterView } from 'vue-router'
import Navbar from './components/NavBar.vue'

export default {
  name: 'App',
  components: {
    Navbar
  }
}
</script>

