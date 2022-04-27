<template>
  <div class="container mt-5">
    <div class="row row-cols-5 g-5">
      <!--inserire contenuto componente-->
      <CardSerie v-for="(element, index) in props2Serie" :key="'A'+index" :serie="element"/>
    </div>
    
  </div>
  
</template>

<script>
  import CardSerie from './CardSerie.vue'
export default {
  //Cambiare il nome con quello del componente creato
  name: 'SerieComp',
   components:{
     CardSerie
  },
   props:{
     props2Serie: Array
   }
}
</script>

<style scoped lang="scss">
 /*Inserire style componente*/
</style>