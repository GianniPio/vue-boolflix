<template>
  <div id="app">
    <MyHeader @importlink="importTitle"/> <!-- prendo in v-model per portarlo nella funzione "importTitle" -->
    <MyMain :listfilms="listfilms"  :listSerie="listSerie"/> <!-- trasferisco gli arrey di film e serie nel main -->
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
      nameFilm: "", // salvo il v-model tramite la funzione
      listfilms: [], // salvo l'array di film che ottengo dalla funzione getFilms
      APIfilm: "https://api.themoviedb.org/3/search/movie?api_key=dd75a648bab4fb373b26c8914bfc572a&language=it-IT&query=", // API dei film
      listSerie: [], // salvo l'array delle serie che ottengo dalla funzione getSerie
      APISerie: "https://api.themoviedb.org/3/search/tv?api_key=dd75a648bab4fb373b26c8914bfc572a&language=it-IT&query=" //API delle serie
    }
  },

  methods: {
    // salvo il v-model dell'header in una variabile, poi chiamo le funzioni getFilms e getSerie
    importTitle(title) {  
      this.nameFilm = title;
      this.getFilms();
      this.getSerie();
    },
    // tramite axios, unisco l'API dei film con il v-model e dal risultato estratto solamente l'array data
    getFilms() {
      axios.get(this.APIfilm + this.nameFilm).then((result) => {
        this.listfilms = result.data.results;  
      })
    },
    // tramite axios, unisco l'API delle serie con il v-model e dal risultato estratto solamente l'array data
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
