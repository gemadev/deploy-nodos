<template>
  <main class="h-screen flex items-center justify-center px-3">
    <div class="container mx-auto grid justify-center">

      <form
        @submit.prevent="search"
        class="rounded-3xl max-w-[461px] py-6 px-10 bg-[#F1EDE3]"
      >

        <p class="font-black text-lg font-display text-[#226B2F] text-center mb-2 p-0">
          ¿estas buscando alojamiento?
        </p>

        <p class="text-md font-display text-[2A2d34] tracking-normal text-center indent-2 w-60 pl-3">
          Encontra la mejor opcion para hospedarte en {Posadas}
        </p>

        <div class="inline-flex px-1 space-x-3 pt-6 pr-2">
        <v-input
          id="dateIn"
          v-model="form.data.dateIn"
          type="text"
          placeholder="Fecha de Entrada"
          class="mb-6"
          onfocus="(this.type='date')"
          :required="true"
          :disabled="form.loading"
        />

        <v-input
          id="dateOut"
          v-model="form.data.dateOut"
          type="text"
          placeholder="Fecha de Salida"
          class="mb-6"
          onfocus="(this.type='date')"
          :required="true"
          :disabled="form.loading"
        />
        </div>

        <div class="flex" id="App">
          <button @click.prevent="ventana=true" class="bg-white rounded-[10px] px-3 py-[18px] w-full block focus:ring-0 focus:outline-0 disabled:opacity-70 disabled:cursor-not-allowed">Pasajeros</button>

          <div v-bind="ventana" v-if="ventana" class="bg-white rounded-[10px] px-3 py-[18px] w-full block focus:ring-0 focus:outline-0 disabled:opacity-70 disabled:cursor-not-allowed">
            <form action="">
              <Counter/>
              <input @click.prevent="ventana=false" type="button" value="Guardar Selecion" class="pt-5">
            </form>
          </div>
        </div>

        <v-button type="submit" :disabled="form.loading">
          <span v-if="form.loading" class="flex justify-center">
            <svg class="animate-spin h-5 w-5 text-white" xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24">
              <circle
                class="opacity-25"
                cx="12"
                cy="12"
                r="10"
                stroke="currentColor"
                stroke-width="4"
              />
              <path class="opacity-75" fill="currentColor" d="M4 12a8 8 0 018-8V0C5.373 0 0 5.373 0 12h4zm2 5.291A7.962 7.962 0 014 12H0c0 3.042 1.135 5.824 3 7.938l3-2.647z"></path>
            </svg>
          </span>

          <span v-else>
            Buscar
          </span>
        </v-button>

        <p class="text-center">
          <NuxtLink to="/terminoycondiciones" class="text-sm text-[#565656]">
            Al buscar acepta Terminos y Condiciones
          </NuxtLink>
        </p>
      </form>
      <banner/>
      <Footer/>
    </div>
  </main>
</template>
<script>
import Banner from '../components/Banner.vue'
import Counter from '../components/Counter.vue'
export default {
  name: 'App',
  components: { Counter, Banner },
  head: {
    title: 'Buscar'
  },
  data () {
    return {
      ventana: false,
      date: '',
      form: {
        loading: false,
        data: {
          dateIn: '',
          dateOut: '',
          pasajeros: ''
        }
      }
    }
  },
  methods: {
    search () {
      if (this.form.data.dateIn || this.form.data.dateOut) {
        this.form.loading = true
        console.log('loading')
      }
    }
  }
}
</script>

<style scoped>
  form {
    box-shadow: 3px 5px 10px rgba(0, 0, 0, 0.05);
  }
</style>
