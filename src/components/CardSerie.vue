<template>
    <div class="card-serie">
        <div class="flip-card">
            <div class="flip-card-inner">
                <div class="flip-card-front">
                    <img :src="`https://image.tmdb.org/t/p/w342/${serie.poster_path}`"
                        style="width:230px;height:300px;">
                </div>
                <div class="flip-card-back">
                    <h6>Titolo: {{serie.name}} </h6>
                    <h6>Titolo originale: {{serie.original_name}} </h6>

                    <span>Lingua: </span>
                    <span
                        :class="(serie.original_language =='en') ? 'fl-en' : (serie.original_language =='it') ? 'fl-it' :'fl-ignoto'" 
                        style="width:25px;height:25px;"
                        >
                        
                    </span>


                    <p>Voto: {{serie.vote_average}}
                        <i v-for="i in 5" :key="i" class="fa-star"
                            :class="(i <= stella()) ? 'fa-solid' : 'fa-regular' "></i>
                    </p>
                    <p class="text-card">Overview: {{serie.overview}}</p>
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
            serie: Object
        },

        methods: {
            stella() {
                const voto = Math.ceil(this.serie.vote_average)
                return voto
            }
        }
    }
</script>

<style scoped lang="scss">
    /*Inserire style componente*/

    .card-serie {
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
        color: rgba(255, 255, 0, 0.789);
    }

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
        color: white;
        transform: rotateY(180deg);
        overflow-y: auto;
    }
</style>