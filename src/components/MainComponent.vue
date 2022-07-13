<!-- HTML -->
<template>
    <div class="container">
        <ul>
            <CardFilm v-for="(film, index) in infoFilm" :key="index" :item="film" />

        </ul>
        
    </div>

    
</template>

<!-- JAVASCRIPT -->
<script>
import CardFilm from './CardFilm'
// import axios from 'axios'

export default {
    name: 'MainComponent',
    components: {
        CardFilm,
    },

    props: {
        "infoFilm": Array,
        "searching": Boolean

    },

    data(){
        return{
            // arrayFilm:[],
            // url: 'https://api.themoviedb.org/3/movie/550?api_key=553b5aa9ad4d3b90c09c3a4569be72aa',
            // getResult: '',
        }

    },
    
}
</script>

<!-- CSS -->
<style lang="scss" scoped>
ul{
    display: flex;
    flex-wrap: wrap;
}

</style>