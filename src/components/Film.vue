<template>
  <div class="elefilm">
    <p><span>Titolo:</span> {{details.title}}</p>
    <p><span>Titolo originale:</span> {{details.original_title}}</p>
    <p><span>Lingua:</span> {{details.original_language}}</p>
    <p><span>Voto:</span> {{details.vote_average}}</p>
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
        width: calc(95% / 3);
        margin: 10px;
        background-color: rgb(73, 73, 73) ;

        border: 1px solid white;
        text-align: center;

        p {
            margin: 10px;
            color: white;

            span {
                color: red;
            }
        }

    }

</style>
