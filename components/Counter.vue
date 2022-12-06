<template>
    <div>
    <h3  class="inline-flex px-1 space-x-1 pt-6 pr-1">Adultos</h3>
    <button @click="decrement" class="inline-flex px-1 space-x-1 pr-0">-</button>
    <h3 class="inline-flex px-1 space-x-1 pt-6 pr-1">{{ counterValue }}</h3>
    <button @click="increment" class="inline-flex px-1 space-x-1 pr-0">+</button>
    <h3  class="inline-flex px-1 space-x-1 pt-6 pr-1">Niños</h3>
    <button @click="decrementChild" class="inline-flex px-1 space-x-1 pr-0">-</button>
    <h3 class="inline-flex px-1 space-x-1 pt-6 pr-1">{{ counterChild }}</h3>
    <button @click="incrementChild" class="inline-flex px-1 space-x-1 pr-0">+</button>
    </div>
</template>

<script>

export default {
  name: 'Counter',
  data () {
    return {
      counterValue: 0,
      counterChild: 0
    }
  },
  methods: {
    increment () {
      this.counterValue++
    },
    decrement () {
      if (this.counterValue >= 1) {
        this.counterValue--
      }
    },
    incrementChild () {
      this.counterChild++
    },
    decrementChild () {
      if (this.counterChild >= 1) {
        this.counterChild--
      }
    }
  }
}
</script>
