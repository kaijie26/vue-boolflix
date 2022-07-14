<!-- HTML -->
<template>
    <main>
        <!-- FILM -->
        <h2>Film</h2>
        <ul>
            <CardFilm v-for="(film) in infoFilm" :key="film.id" :item="film" />

        </ul>
        
        <!-- SERIE TV -->
        <h2>Serie Tv</h2>
        <ul>
            <CardFilm v-for="(serie) in infoSeries" :key="serie.id" :item="serie" />

            
        </ul>
        
    </main>

    
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
        "infoSeries": Array,
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