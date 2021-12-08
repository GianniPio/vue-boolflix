<template>
  <div class="elefilm">
    <div class="img_film">
      <img :src='"https://image.tmdb.org/t/p/w300" + details.poster_path' :alt="details.original_title || details.original_name">
    </div>
    
    <div class="descr_film">
      <p><span>Titolo:</span> {{details.title || details.name}}</p>
    <p><span>Titolo originale:</span> {{details.original_title || details.original_name}}</p>
    <p><span>Data di uscita:</span> {{details.release_date || details.first_air_date}}</p>
    <p>
      <span>
        <div class="flag">
            <img :src="flagLanguage(details.original_language)" :alt="details.original_language">
        </div>
      </span>
    </p>
    <p>
      <span>Voto:</span> 
      <i class="fas fa-star yellow" v-for="star, x in newVoto" :key="x">
      </i><i class="far fa-star" v-for="empty, y in maxVote - newVoto" :key="y"></i>
    </p>
    <p><span>Overview:</span>{{details.overview}} </p>
</div>
    
  </div>
</template>

<script>
export default {
  name: 'Film',
  props: {
      details: Object,
  },
  data() {
    return {
      // voto in base 5
      newVoto: Math.ceil(this.details.vote_average / 2),
      maxVote: 5,
    }
    
  },
  methods: {
    // funzione che stampa le bandiere
    // volevo fare in modo che la lingua fosse uguale al nome di un immagine che salvavo in img, in modo da semplificare ancora la funzione, ma non mi leggeva l'immagine e ho cambiato ragionamento
    flagLanguage(lingua) {
      return require("@/assets/img/"+lingua+".jpg")
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">

  .elefilm {
  width: calc(95% / 3);
  margin: 10px;
  background-color: rgb(73, 73, 73);
  position: relative;
  height: 500px;

  border: 1px solid white;
  text-align: center;

  .img_film {
    z-index: 1;
    width: 100%;
    position: absolute;
    height: 100%;
    
    img {
      height: 100%;
      width: 100%;
    }

    &:hover{
      filter: opacity(0);
    }

  }

  .descr_film {

    position: absolute;
    top: 5%;
    text-align: left;
    font-size: 15px;

    p {
      margin: 10px;
      color: white;

      span {
        color: red;
      }

      .flag {
        width: 60px;
        margin: 0 auto;

        img {
          object-fit: contain;
          width: 100%;
        }
      }
    }
  }

  .yellow {
    color: yellow;
  }

  .white {
    color: white;
  }

}

</style>
