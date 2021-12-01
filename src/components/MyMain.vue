<template>
  <main>
    <Film v-for="film, i in listfilms" :key="i" :details="film"/>
  </main>
</template>

<script>

import Film from '@/components/Film.vue';
import axios from "axios";


export default {
  name: 'MyMain',
  components: {
    Film,
  },
  data() {
    return {
      listfilms: [],
      APIfilm: "https://api.themoviedb.org/3/search/movie?api_key=dd75a648bab4fb373b26c8914bfc572a&query=" + this.titleFilm,
    }
  },
  props: {
    titleFilm : String,
  },
  created() {
    this.getFilms();
  },
  methods: {
    getFilms() {
      axios.get(this.APIfilm).then((result) => this.listfilms = result.data.results)
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">

main {
  padding: 15px;
  background-color: grey;
  display: flex;
  flex-wrap: wrap;
}
</style>
