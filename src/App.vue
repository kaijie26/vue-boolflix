<template>
  <div id="app">
    <HeaderComponent @searchedFilm= 'apiFilm' />
    <MainComponent :infoFilm='userChoose' />
    
  </div>
</template>

<script>
import HeaderComponent from './components/HeaderComponent.vue'
import MainComponent from './components/MainComponent.vue'

export default {
  name: 'App',
  components: {
    HeaderComponent,
    MainComponent,
  },

  data() {
    return{
      userChoose: '',

    }
  },

  methods: {
    apiFilm(result){
      this.userChoose = result;

    }

  },

  created() {
    this.apiFilm;
  }

  
}
</script>

<style lang="scss">
@import './style/common';

</style>
