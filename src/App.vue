<template>
  <div class="ciccio">
    <HeaderComp @inviaTesto="cercaTesto" />

    <MainComp :propsFilm="moviesArray" :propsSerie="tvArray" />
  </div>
</template>

<script>
  import "bootstrap"
  import HeaderComp from './components/HeaderComp.vue'
  import MainComp from './components/MainComp.vue'
  import axios from 'axios'
  export default {
    name: 'App',
    components: {
      HeaderComp,
      MainComp,
    },

    data() {
      return {
        moviesArray: [],
        tvArray: [],
        apiKey: '1e3cd7808e66baf68401346fc5900323',
        testoRicerca: '',
      }
    },
    computed: {},

    methods: {
      cercaTesto(filmCercato) {
        axios.get(
            `https://api.themoviedb.org/3/search/movie?api_key=1e3cd7808e66baf68401346fc5900323&query=${filmCercato}`)
          .then((res) => {
            //Controllo delle informazioni che otteniamo alla chiamata
            console.log(res.data.results);
            //Modifica dell'array dove salveremo i dati
            this.moviesArray = res.data.results

          })
        axios.get(
            `https://api.themoviedb.org/3/search/tv?api_key=1e3cd7808e66baf68401346fc5900323&query=${filmCercato}`)
          .then((res) => {
            //Controllo delle informazioni che otteniamo alla chiamata
            console.log(res.data.results);
            //Modifica dell'array dove salveremo i dati

            this.tvArray = res.data.results
          })

      }

    }
  }
</script>

<style lang="scss">
  @import "bootstrap/dist/css/bootstrap.min.css";

  .ciccio {
    background-color: rgba(86, 85, 85, 0.785);
    height: 100%;
  }
</style>