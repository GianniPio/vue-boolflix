<template>
  <header>
    <div id="title">
        <p>BOOLFLIX</p>
    </div>
    <div id="nav">
      <form action="">
        <input v-model="link" type="text" placeholder="Inserisci il titolo di un film">
        <button @click="$emit('importlink', link)">Cerca</button>
      </form>
    </div>
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
    display: flex;
    justify-content: space-between;

    #title {

      p {
          color: red;
          font-size: 20px;
          padding: 20px;
      }
        
    }

    #nav {
      padding: 20px;

      input {
        height: 25px;
        padding: 15px 15px 15px 5px;
      }


      button {
        cursor: pointer;
        height: 25px;
        margin-left: 5px;
        padding: 15px;
        line-height: 10%;
      }
    }
}

</style>
