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
    <p><span>Voto:</span> <i class="fas fa-star yellow" v-for="star, x in newVoto" :key="x"></i> </p>
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
      maxVote: 5
    }
    
  },
  methods: {
    // funzione che stampa le bandiere
    // volevo fare in modo che la lingua fosse uguale al nome di un immagine che salvavo in img, in modo da semplificare ancora la funzione, ma non mi leggeva l'immagine e ho cambiato ragionamento
    flagLanguage(lingua) {
      if (lingua == "it") {
        return "https://upload.wikimedia.org/wikipedia/commons/c/ca/Bandiera_italiana_foto.svg"
      } else if (lingua == "en") {
        return "https://www.novalibandiere.it/wp-content/uploads/granbretagna.gif"
      } else if (lingua == "fr") {
        return "https://upload.wikimedia.org/wikipedia/commons/thumb/3/3a/Flag_of_France_%281794%E2%80%931815%2C_1830%E2%80%931958%29.svg/280px-Flag_of_France_%281794%E2%80%931815%2C_1830%E2%80%931958%29.svg.png"
      } else if (lingua == "es") {
        return "https://m.media-amazon.com/images/I/41vY+lH0M2L._AC_SX425_.jpg"
      } else {
        return "https://www.rainews.it/dl/img/2018/11/310x0_1541418990687.earth_11015_1920.jpg"
      }
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">

  .elefilm {
  width: 23.4848833%;
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
    top: 80%;
    left: 50%;
    height: 100%;
    width: 100%;
    transform: translate(-50%, -50%);

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

}

</style>
