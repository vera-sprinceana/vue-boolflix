<template>
  <div>
    <HeaderComp @inviaTesto="cercaTesto"/>
    <MainComp
     v-for="(element, index ) in moviesArray"
    :key="index"
    />
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
  data(){
    return{
      moviesArray:[],
      apikey: '1e3cd7808e66baf68401346fc5900323',
      testoRicerca:'',
    }
  },
  created(){
     axios.get('https://api.themoviedb.org/3/movie/76341?api_key=1e3cd7808e66baf68401346fc5900323&${testoRicerca}')
         .then( ( res )=>{
           //Controllo delle informazioni che otteniamo alla chiamata
           console.log( res.data );
           //Modifica dell'array dove salveremo i dati
           this.moviesArray = res.data
         } )
         //Salvataggio in console di possibili errori
         .catch( (error) => {
           console.log( error )
         } )
  },
  methods: {
    cercaTesto(text){
      this.testoRicerca=text
    }
  }
}
</script>

<style lang="scss">
@import "bootstrap/dist/css/bootstrap.min.css";
</style>
