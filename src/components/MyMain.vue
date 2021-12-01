<template>
  <main>
    <Film/>
  </main>
</template>

<script>

import Film from '@/components/Film.vue';


export default {
  name: 'MyMain',
  components: {
    Film,
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">

main {
  height: 100vh;
  background-color: grey;
}
</style>
