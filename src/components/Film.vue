<template>
  <div class="elefilm">
    <p><span>Titolo:</span> {{details.title}}</p>
    <p><span>Titolo originale:</span> {{details.original_title}}</p>
    <p>
      <span v-if="(details.original_language === 'it')">
        <div class="flag">
            <img src="https://upload.wikimedia.org/wikipedia/commons/thumb/c/ca/Bandiera_italiana_foto.svg/1024px-Bandiera_italiana_foto.svg.png" :alt="details.original_language">
        </div>
      </span>
      <span v-else-if="(details.original_language === 'en')">
        <div class="flag">
          <img src="https://www.novalibandiere.it/wp-content/uploads/granbretagna.gif" :alt="details.original_language">
        </div>
      </span>
      <span v-else-if="(details.original_language === 'pt')">
        <div class="flag">
          <img src="https://www.novalibandiere.it/wp-content/uploads/portogallo.gif" :alt="details.original_language">
        </div>
      </span>
      <span v-else-if="(details.original_language === 'es')">
        <div class="flag">
          <img src="https://www.transumanzapedali.it/wp-content/uploads/2020/07/spain-2906824_640.png" :alt="details.original_language">
        </div>
      </span>
      <span v-else-if="(details.original_language === 'sv')">
        <div class="flag">
          <img src="https://upload.wikimedia.org/wikipedia/commons/thumb/4/4c/Flag_of_Sweden.svg/2000px-Flag_of_Sweden.svg.png" :alt="details.original_language">
        </div>
      </span>
      <span v-else-if="(details.original_language === 'fr')">
        <div class="flag">
          <img src="https://i.ebayimg.com/images/g/L10AAOSwzk5ej4co/s-l300.jpg" :alt="details.original_language">
        </div>
      </span>
      <span v-else-if="(details.original_language === 'hr')">
        <div class="flag">
          <img src="https://www.novalibandiere.it/wp-content/uploads/Croazia.jpg" :alt="details.original_language">
        </div>
      </span>
      <span v-else-if="(details.original_language === 'de')">
        <div class="flag">
          <img src="https://www.cosepercrescere.it/wp-content/uploads/2014/06/GERMANIA.jpg" :alt="details.original_language">
        </div>
      </span>
      <span v-else>
        {{details.original_language}}
      </span>
    </p>
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

</style>
