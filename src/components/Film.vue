<template>
  <div class="elefilm">
    <span>{{details.title}}</span>
    <span>{{details.original_title}}</span>
    <span>{{details.original_language}}</span>
    <span>{{details.vote_average}}</span>
  </div>
</template>

<script>
export default {
  name: 'Film',
  props: {
      details: Object,
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">

    .elefilm {

        width: calc(100% / 3);

        img {
            border: 1px solid white;
        }
    }

</style>
