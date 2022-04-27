<template>
  <div class="container pt-2 bg_custom">
    <!--inserire contenuto componente-->
    <div class="">
      <FilmComp :props2Film="propsFilm"/>
      <SerieComp :props2Serie="propsSerie"/>
    </div>  
  </div>
</template>

<script>
import FilmComp from './FilmComp.vue'
import SerieComp from './SerieComp.vue'
export default {
  //Cambiare il nome con quello del componente creato

  name: 'MainComp',
  components:{
      FilmComp,
      SerieComp,
  },
   props: {
     propsFilm: Array,
     propsSerie: Array,
   },
  data(){
    return {
      
    }
  }
}
</script>

<style scoped lang="scss">
 /*Inserire style componente*/

 

</style>