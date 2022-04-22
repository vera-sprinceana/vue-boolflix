<template>
  <div>
    <!--inserire contenuto componente-->
    ciao
    <FilmCard/>
    <CardSeriestv/>
  </div>
</template>

<script>
import FilmCard from './FilmCard.vue'
import CardSeriestv from './CardSeriestv.vue'
export default {
  //Cambiare il nome con quello del componente creato

  name: 'MainComp',
  componente:{
      FilmCard,
      CardSeriestv,
  }
}
</script>

<style scoped lang="scss">
 /*Inserire style componente*/
 div{
     background-color: grey;
 }
</style>