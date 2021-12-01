<template>
  <div id="app">
    <MyHeader @importlink="importTitle"/>
    <MyMain :titleFilm="nameFilm"/>
  </div>
</template>

<script>

import MyHeader from './components/MyHeader.vue';
import MyMain from './components/MyMain.vue';


export default {
  name: 'App',
  components: {
    MyHeader,
    MyMain,
  },
  data() {
    return {
      nameFilm: "",
    }
  },

  methods: {
    importLink(link) {
      this.nameFilm = link;
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
