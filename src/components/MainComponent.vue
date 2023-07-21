<script>

    import {store} from '../store.js'
    import axios from 'axios'
    import Card from '../components/Card.vue'

    export default {
        
        data() {
        return{
            
            store,

        }
        },

        methods: {
            
            
        },

        components: {
            
            Card,
        },
        
        props:{
            
        }

    }

</script>


<template>

    <main>
        
        <h3 class="text-white mt-5 m-2">
            I Più Popolari
        </h3>

        <div class="d-flex card-row">
            
            
            <div class="movie_card mb-5" v-for="(singlePopularMovie, index) in store.popularMovie" :key="index">
                <Card :elementData="singlePopularMovie"/>
            </div> 
            
        </div>
        
     

        <h3 class="text-white mt-5 ms-2" id="movie">
            Film
        </h3>

        <div class="d-flex card-row">
        
            <div v-if="store.movie.length > 0" class="d-flex">

                <div class="movie_card mb-5" v-for="(singleMovie, index) in store.movie" :key="index">
                    <Card :elementData="singleMovie"/>
                </div>

            </div>

            <div v-else>

                <h3 class="overflow-y-hidden pt-2 ms-2">
                   Nessun risultato ottenuto
                </h3>

            </div>

        </div>
        
        <h3 class="text-white mt-5 ms-2" id="series">
            Serie Tv
        </h3>
        

        <div class="d-flex card-row">

            <div v-if="store.serietv.length > 0" class="d-flex">

                <div class="movie_card series" v-for="(singleSeries, index) in store.serietv" :key="index">
                    <Card :elementData="singleSeries"/>
                </div>

            </div>

            <div v-else>

                <h3 class="overflow-y-hidden pt-2 ms-2">
                   Nessun risultato ottenuto
                </h3>

            </div>

        </div>
    
    </main>

</template>




<style lang="scss" scoped>

    @use '../assets/scss/variables.scss' as *;

    main {
        background-image: linear-gradient(
            40deg,
            hsl(358deg 75% 48%) 27%,
            hsl(359deg 70% 50%) 51%,
            hsl(360deg 70% 51%) 58%,
            hsl(1deg 70% 52%) 61%,
            hsl(1deg 70% 53%) 62%,
            hsl(2deg 70% 54%) 63%,
            hsl(2deg 71% 55%) 64%,
            hsl(3deg 67% 53%) 65%,
            hsl(5deg 64% 51%) 66%,
            hsl(6deg 61% 50%) 67%,
            hsl(7deg 61% 48%) 68%,
            hsl(8deg 62% 47%) 70%,
            hsl(9deg 63% 45%) 73%,
            hsl(3deg 58% 46%) 76%,
            hsl(357deg 59% 45%) 79%,
            hsl(351deg 64% 43%) 84%,
            hsl(345deg 70% 40%) 88%,
            hsl(340deg 77% 38%) 94%,
            hsl(335deg 84% 35%) 100%
        );
        padding: 20px 30px;
    }
    .card-row{
        overflow-x: auto;
    }
    .movie_card {
        width: 200px;
        height: 250px;
        text-align: center;
        margin: 10px 10px;
        flex-shrink: 0;
        box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
        transition: box-shadow 0.3s ease;
    }

    .img_movie {
        height: 250px;
        position: relative;
        
        
        img {
            width: 100%;
            height: 100%;
            object-fit: cover;
        }
    }

    .description {
        display: none;
        width: 200px;
        background-color: rgba(0,0,0,0.8);
        padding: 15px;
        color: white;
        overflow-y: auto;
        font-size: 1em;

        
        .flag_box {
            width: 15px;
            height: 10px;
            margin-bottom: 20px;
            margin-left: calc(150px / 2);

            img {
                width: 100%;
            }
        }

        .fa-star{
            padding-top: 10px;
            color: gold;
        }

        .overview{
            font-size: 0.8em;
        }
    }

    .img_movie:hover .description {
        display: block;
        position: absolute;
        top: 0;
        bottom: 0;
        right: 0;
        left: 0;
        box-shadow: 0 8px 16px rgba(0, 0, 0, 0.2);
    }

</style>