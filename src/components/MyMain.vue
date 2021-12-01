<template>
  <main>
    <Film v-for="film, i in listfilms" :key="i" :details="film"/>
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
  },
  created() {
    this.getFilms();
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
