<script>

   export default {

    data() {
      return{
        
      }
    },

    methods: {
        
    },

    computed: {

        vote(){
            
            const finalVote = Math.ceil(this.elementData.vote_average / 2 );
            return finalVote
        },

        flag(){

            if(this.elementData.original_language == 'en'){
                return 'https://flagicons.lipis.dev/flags/4x3/gb.svg'
            }
            else if(this.elementData.original_language == 'it'){
                return 'https://flagicons.lipis.dev/flags/4x3/it.svg'
            }
            else if(this.elementData.original_language == 'fr'){
                return 'https://flagicons.lipis.dev/flags/4x3/fr.svg'
            }
            else if(this.elementData.original_language == 'sp'){
                return 'https://flagicons.lipis.dev/flags/4x3/sp.svg'
            }
            else if(this.elementData.original_language == 'de'){
                return 'https://flagicons.lipis.dev/flags/4x3/de.svg'
            }
            else if(this.elementData.original_language == 'ja'){
                return 'https://flagicons.lipis.dev/flags/4x3/ja.svg'
            }
            else if(this.elementData.original_language == 'hi'){
                return 'https://flagicons.lipis.dev/flags/4x3/in.svg'
            }
            else if(this.elementData.original_language == 'kr'){
                return 'https://flagicons.lipis.dev/flags/4x3/kr.svg'
            }
            else{
                return 'https://flagicons.lipis.dev/flags/4x3/xx.svg'
            }

        }
        
    },

    props:{

        elementData: {
            type: Object,
            default: null
        }
    }
    
  }
</script>


<template>
    
    <div>

        <div class="img_movie">

            <img v-if="elementData.backdrop_path == null" src="../assets/img/notfound.png" alt="">

            <img v-else :src="`https://image.tmdb.org/t/p/original${elementData.backdrop_path}`" alt="" class="img-fluid">
            
            <div class="card_data">
    
                <p>
    
                    <span>
                        Titolo: 
                    </span>

                    {{ elementData.title ?? elementData.name }}

                </p>
    
                <p>

                    <span>
                        Titolo originale:
                    </span>

                    {{ elementData.original_title ?? elementData.original_name }}

                </p>
    
                <span>

                    Voto:
                    <span>
                        {{ vote }}
                    </span>
    
                    <i v-for="num in vote" :key="num" class="fa-solid fa-star"></i>
                    <i  v-for="num in (5 - vote)" :key="num" class="fa-regular fa-star"></i>

                </span>
                
                <div class="flag_box mt-1">
                    <img :src="flag" alt="">
                </div>

                <p class="overview">
                    {{ elementData.overview }}
                </p>
            
            </div>

        </div>

    </div>

</template>



<style lang="scss" scoped>

    @use '../assets/scss/variables.scss' as *;
    .img_movie {
        height: 250px;
        position: relative;
        
        img {
            width: 100%;
            height: 100%;
            object-fit: cover;
        }
    }

    .card_data {
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

    .img_movie:hover .card_data {
        display: block;
        position: absolute;
        top: 0;
        bottom: 0;
        right: 0;
        left: 0;
    }
    
</style>