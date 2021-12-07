<template>
  <div id="app">
    <MyHeader @importlink="importTitle"/>
    <MyMain :listfilms="listfilms"  :listSerie="listSerie"/>
  </div>
</template>

<script>

import MyHeader from './components/MyHeader.vue';
import MyMain from './components/MyMain.vue';
import axios from "axios";

export default {
  name: 'App',
  components: {
    MyHeader,
    MyMain,
  },
  data() {
    return {
      nameFilm: "",
      listfilms: [],
      APIfilm: "https://api.themoviedb.org/3/search/movie?api_key=dd75a648bab4fb373b26c8914bfc572a&language=it-IT&query=",
      listSerie: [],
      APISerie: "https://api.themoviedb.org/3/search/tv?api_key=dd75a648bab4fb373b26c8914bfc572a&language=it-IT&query="
    }
  },

  methods: {
    importTitle(title) {
      this.nameFilm = title;
      this.getFilms();
      this.getSerie();
    },
    getFilms() {
      axios.get(this.APIfilm + this.nameFilm).then((result) => {
        this.listfilms = result.data.results;  
      })
    },
    getSerie() {
      axios.get(this.APISerie + this.nameFilm).then((result) => {
        this.listSerie = result.data.results;
        console.log(result.data.results)
      })
    }
  }
}
</script>

<style lang="scss">
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
}

* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}
</style>
