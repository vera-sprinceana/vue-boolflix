<template>
  <div class="card">
    <div class="flip-card">
      <div class="flip-card-inner">
        <div class="flip-card-front">
          <img :src="`https://image.tmdb.org/t/p/w342/${film.poster_path}`" 
          style="width:230px;height:300px;">
        </div>
        <div class="flip-card-back text-center">
          <h6>Titolo: {{film.title}} </h6>
          <h6>Titolo originale: {{film.original_title}} </h6>

          <span>Lingua: </span>
          <span
            :class="(film.original_language =='en') ? 'fl-en' : (film.original_language =='it') ? 'fl-it' :'fl-ignoto'">
          </span>


          <p>Voto: {{film.vote_average}}
            <i v-for="i in 5" :key="i" class="fa-star" :class="(i <= stella()) ? 'fa-solid' : 'fa-regular' "></i>
          </p>
          <p class="text-card">Overview: {{film.overview}}</p>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
  export default {
    //Cambiare il nome con quello del componente creato
    name: 'CardComp',
    components: {

    },
    props: {
      film: Object,
    },
    methods: {
      stella() {
        const voto = Math.ceil(this.film.vote_average)
        return voto
      }
    }
  }
</script>

<style scoped lang="scss">
  /*Inserire style componente*/
  .card {
    width: 230px;
    height: 300px;
    background-color: grey;
  }

  .text-card {
    color: grey;
  }

  .fl-en {
    background-image: url('../assets/img/icons8-gran-bretagna-48.png');
    background-size: cover;
    background-repeat: no-repeat;
    width: 25px;
    height: 25px;
  }

  .fl-it {
    background-image: url('../assets/img/icons8-italia-16.png');
    background-size: cover;
    background-repeat: no-repeat;
    width: 25px;
    height: 25px;
  }

  .fl-ignoto {
    background-image: url('../assets/img/icons8-bandiera-vuota-16.png');
    background-size: cover;
    background-repeat: no-repeat;
    width: 25px;
    height: 25px;
  }

  .fa-star {
    color: rgba(255, 255, 0, 0.904);
  }

  // effetto 3D
  .flip-card {
    background-color: transparent;
    width: 200px;
    height: 300px;
    perspective: 1000px;
  }

  .flip-card-inner {
    position: relative;
    width: 100%;
    height: 100%;
    text-align: center;
    transition: transform 0.6s;
    transform-style: preserve-3d;
    box-shadow: 0 4px 8px 0 rgba(0, 0, 0, 0.2);
  }

  .flip-card:hover .flip-card-inner {
    transform: rotateY(180deg);
  }

  .flip-card-front,
  .flip-card-back {
    position: absolute;
    width: 100%;
    height: 100%;
    -webkit-backface-visibility: hidden;
    backface-visibility: hidden;
  }

  .flip-card-front {
    background-color: #bbb;
    color: black;
  }

  .flip-card-back {
    background-color: #020202;
    background-size: cover;
    overflow-y: auto;
    color: white;
    transform: rotateY(180deg);
  }
</style>