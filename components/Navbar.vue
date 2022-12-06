<template>
    <div>
        <span @click="MenuOpen()" class="absolute md:hidden right-6 top-1.5 cursor-pointer text-4xl z-5">
            <i :class="[open ? 'bi bi-x' : 'bi bi-list']"></i>
        </span>
        <ul class="w-9/12 md:flex md:items-center md:px-0 px-3 md:pb-0 pb-10 md:static absolute bg-gray-50 md:w-10 h-full top-10 duration-700 ease-in"
        :class="[open ? 'translate-x-px400' : 'translate-x-[-400px hidden']">
        <li class="md:mx-4 md:my-0 my-6" v-for="link in Links" :key="link.link">
            <a :href=link.link class="text-xl hover:text-green-700">{{link.name}}</a>
        </li>
    </ul>
</div>
</template>

<script>
import { ref } from 'vue'

export default {
  setup () {
    const open = ref(false)
    const Links = [
      { name: 'Inicio', link: '#' },
      { name: 'Política de Privacidad', link: '#' },
      { name: 'Términos y condiciones', link: '#' }
    ]
    function MenuOpen () {
      open.value = !open.value
    }
    return { Links, open, MenuOpen }
  }

}
</script>

<style>
  @import "bootstrap-icons/font/bootstrap-icons.css";
</style>
