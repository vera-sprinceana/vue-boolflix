<template>
  <div class="container">
    <div class="row row-cols-5 g-5">
      <!--inserire contenuto componente-->
       <CardFilm v-for="(elem, index) in props2Film" :key="index" :film="elem"/>
    </div>
    
  </div>
</template>

<script>
import CardFilm from './CardFilm.vue'
export default {
  //Cambiare il nome con quello del componente creato
 
  name: 'FilmComp',
  components:{
    CardFilm
  },
   props:{
    props2Film: Array
   }
}
</script>

<style scoped lang="scss">
 /*Inserire style componente*/
 
</style>