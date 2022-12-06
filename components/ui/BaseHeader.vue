<template>
    <header class="flex justify-left p-2 mr-1">
        <img class="h-12" src="../../assets/images/logo.png" alt="Logo">
        <Navbar />
    </header>
</template>

<script>
import Navbar from '../Navbar.vue'
export default {
  name: 'BaseHeader',
  components: {
    Navbar
  }
}
</script>
