<script>

  import HeaderComponent from './components/HeaderComponent.vue';
  import MainComponent from './components/MainComponent.vue';

  import {store} from './store.js'

  import axios from 'axios';

  export default {

    data() {
      return{
        store,
      }
    },

    components: {

      HeaderComponent,
      MainComponent,

    },

    methods: {

      getMovie(){

          axios.get('https://api.themoviedb.org/3/search/movie?api_key=1ca56690c738fe07273dfdadfc643ca2', {
                    params: {
                        query: this.store.searchBar
                       
                    }
                })
        .then(response => {
          this.store.movie = response.data.results;
        })

      },

      getSeries(){

          axios.get('https://api.themoviedb.org/3/search/tv?api_key=1ca56690c738fe07273dfdadfc643ca2', {
                    params: {
                      query: this.store.searchBar
                       
                    }
                })
        .then(response => {
          this.store.serietv = response.data.results;
        })

      },

      getPopularMovie(){

          axios.get('https://api.themoviedb.org/3/tv/popular?api_key=1ca56690c738fe07273dfdadfc643ca2', {
                    params: {
                      page: 1,
                    }
                })
        .then(response => {
          this.store.popularMovie = response.data.results;
          
        })

      },

      searchMovie(){
        this.getMovie();
        this.getSeries();
        
      },
      
    },

    created(){

      this.getMovie();
      this.getSeries();
      this.getPopularMovie()

    }
  }

</script>



<template>

  <div>

    <HeaderComponent @search="searchMovie()"/>

    <MainComponent/>

  </div>

</template>




<style lang="scss">

@use 'assets/scss/main.scss';


</style>