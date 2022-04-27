<template>
  <header class="d-flex justify-content-between align-items-center">
    <!--inserire contenuto componente-->
    <h1 class="ms-3 ">boolflix</h1>
    <input type="text" class="me-3"
    v-model="searchMovie"
    @keydown.enter.prevent="$emit('inviaTesto', searchMovie)"
    >
  </header>
</template>

<script>
export default {
  //Cambiare il nome con quello del componente creato
  name: 'HeaderComp',
  data(){
      return{
          searchMovie:''
      }
  }
}
</script>

<style scoped lang="scss">
 /*Inserire style componente*/
 header{
     background-color: black;
     h1{
         color: rgb(173, 25, 25);
         text-transform: uppercase;
     }
 }
</style>