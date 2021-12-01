<template>
  <header>
    <div id="title">
        <p>BOOLFLIX</p>
    </div>
    <div></div>
  </header>
</template>

<script>
export default {
  name: 'MyHeader',
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">

header {
    background-color: black;

    #title {

        p {
            color: red;
            font-size: 20px;
            padding: 20px;
        }
        
    }
}

</style>
