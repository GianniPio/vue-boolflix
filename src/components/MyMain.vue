<template>
  <main>
    <Film v-for="film, i in listfilms" :key="i" :details="film"/> <!-- Per ogni film che si trova nell'array, crea un details con riferimento film -->
    <Film v-for="serie, i in listSerie" :key="i" :details="serie"/> <!-- Per ogni serie che si trova nell'array, crea un details con riferimento serie -->
  </main>
</template>

<script>

import Film from '@/components/Film.vue';

export default {
  name: 'MyMain',
  components: {
    Film,
  },
  // prende le props dall'app
  props: {
    listfilms : Array,
    listSerie : Array,
  }
}
</script>


<style scoped lang="scss">

main {
  padding: 15px;
  background-color: grey;
  display: flex;
  flex-wrap: wrap;
}
</style>
