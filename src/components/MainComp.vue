<template>
  <div class="container pt-2">
    <!--inserire contenuto componente-->
    <div>
      <h1 class="text-white mb-5">Films</h1>
      <FilmComp :props2Film="propsFilm" />
      <h1 class="text-white">Serie Tv</h1>
      <SerieComp :props2Serie="propsSerie" />
    </div>
  </div>
</template>

<script>
  import FilmComp from './FilmComp.vue'
  import SerieComp from './SerieComp.vue'
  export default {
    //Cambiare il nome con quello del componente creato

    name: 'MainComp',
    components: {
      FilmComp,
      SerieComp,
    },
    props: {
      propsFilm: Array,
      propsSerie: Array,
    },
    data() {
      return {

      }
    }
  }
</script>

<style scoped lang="scss">
  /*Inserire style componente*/
</style>