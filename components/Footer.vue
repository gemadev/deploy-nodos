<template>
    <footer class="table-row justify-center p-1 text-center mt-4 text-xs">
            <p class="justify-center p-1 text-center font-medium text-[#919191]">{{ footerText1 }}</p>
            <p class="justify-center p-1 text-center text-[#919191]">{{ footerText2 }}</p>
            <p class="justify-center p-1 text-center font-medium text-[#919191]">{{ footerText3 }}</p>
    </footer>
</template>

<script>
export default {
  name: 'FooterT',
  data () {
    return {
      footerText1: '¿Necesitas ayuda?',
      footerText2: 'Contactate con nuestros asesores',
      footerText3: '0800-000-0000'
    }
  }
}
</script>
