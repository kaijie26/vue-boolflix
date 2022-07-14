<template>
  <div id="app">
    <HeaderComponent @searchedFilm="search"/>
    <MainComponent :infoFilm="arrayFilm" :infoSeries="arraySeriesTv"  :searching="searchStarted" />
    
  </div>
</template>

<script>
import HeaderComponent from './components/HeaderComponent.vue'
import MainComponent from './components/MainComponent.vue'
import axios from "axios";

export default {
  name: 'App',
  components: {
    HeaderComponent,
    MainComponent,
  },

  data() {
    return{
      userChoose: '',
      arrayFilm:[],
      arraySeriesTv: [],
      allResults:[],
      apiUrl: 'https://api.themoviedb.org/3/search/',
      apiKey: '553b5aa9ad4d3b90c09c3a4569be72aa',
      getResult: '',
      searchStarted: false
      

    }
  },

  methods: {

    // Faccio la chiamata axios del api
    // Tutti i film nel l'api li metto dentro un array
    // Il risultato che cerca l'utente verrà tavolta mostrato nel array dei risultati che è relativo al array dei film
    getFilms(apiParams){
      axios.get(this.apiUrl + 'movie', apiParams).then((response) => {
        this.arrayFilm = response.data.results;
        this.allResults = this.arrayFilm;
        this.searchStarted = true;

      })

    },

    getSeriesTv(apiParams){
      axios.get(this.apiUrl + 'tv', apiParams).then((response) => {
        this.arraySeriesTv = response.data.results;
        this.allResults = this.arraySeriesTv;
        this.searchStarted = true;

      })

    },

    // Al pssaggio della funzione tramite emit dal header
    // Trasformo la userSearch in un oggetto 
    search(result){
      const paramsObject ={
        params: {
          api_key: this.apiKey,
          query: result,
          language: 'it-IT'
          
        }
        
      };
      
      // Chiama le API
      this.getFilms(paramsObject),
      this.getSeriesTv(paramsObject)

      

    }

  },


  
}
</script>

<style lang="scss">
@import './style/common';

</style>
