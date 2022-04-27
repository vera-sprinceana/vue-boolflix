<template>
  <div class="col text-card">
    <!--inserire contenuto componente-->
    <div class="card"> 
    <img :src="`https://image.tmdb.org/t/p/w500/${serie.poster_path}`" alt="">
    </div>
    <div class="bg-dark text-card card">
        <h6>Titolo: {{serie.name}} </h6>
        <h6>Titolo originale: {{serie.original_name}} </h6>
        <div class="d-flex text-card">
            <span>Lingua: </span>
            <span :class="(serie.original_language =='en') ? 'fl-en' : (serie.original_language =='it') ? 'fl-it' :'fl-ignoto'" ></span>
        </div>
          <p>Voto: {{serie.vote_average}}
              <i v-for="i in 5" :key="i" class="fa-star" :class="(i <= stella()) ? 'fa-solid' : 'fa-regular' "></i>
          </p>
          <p class="text-card">Overview: {{serie.overview}}</p>
    </div>
    
  </div>
  
</template>

<script>
 
export default {
  //Cambiare il nome con quello del componente creato
  name: 'CardComp',
   components:{
      
  },
   props:{
    serie: Object
   },
  
    methods: {
        stella(){
            const voto= Math.ceil(this.serie.vote_average)
            return voto
        }
    }
}
</script>

<style scoped lang="scss">
 /*Inserire style componente*/
 
 .card{
   width: 200px;
   height: 250px;
   overflow-y: scroll;
 }
 .text-card{
     color: grey;
 }
 .fl-en{
     background-image: url('../assets/img/icons8-gran-bretagna-48.png');
     background-size: cover;
     background-repeat: no-repeat;
     width: 25px;
     height: 25px;
 }
 .fl-it{
     background-image: url('../assets/img/icons8-italia-16.png');
     background-size: cover;
     background-repeat: no-repeat;
     width: 25px;
     height: 25px;
 }
 .fl-ignoto{
     background-image: url('../assets/img/icons8-bandiera-vuota-16.png');
     background-size: cover;
     background-repeat: no-repeat;
     width: 25px;
     height: 25px;
 }
 .fa-star{
   color: rgba(255, 255, 0, 0.789);
 }
</style>