<template>
  <main>
    <Film v-for="film, i in listfilms" :key="i" :details="film"/>
    <Film v-for="serie, i in listSerie" :key="i" :details="serie"/>
  </main>
</template>

<script>

import Film from '@/components/Film.vue';


export default {
  name: 'MyMain',
  components: {
    Film,
  },
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
