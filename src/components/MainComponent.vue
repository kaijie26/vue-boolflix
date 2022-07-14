<!-- HTML -->
<template>
    <main>
        <!-- FILM -->
        <div class="film">
            <h2>Film</h2>
            <ul>
                <CardFilm v-for="(film) in infoFilm" :key="film.id" :item="film" />

            </ul>

        </div>

        <!-- SERIE TV -->
        <div class="serie-tv">
            <h2>Serie Tv</h2>
            <ul>
                <CardFilm v-for="(serie) in infoSeries" :key="serie.id" :item="serie" />

                
            </ul>

        </div>
        
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
            
        }

    },
    
}
</script>

<!-- CSS -->
<style lang="scss" scoped>
main{
    background-color: #434343;
    display: flex;
    flex-direction: column;
    
}

ul{
    display: flex;
    flex-wrap: wrap;
}

h2{
    padding: 20px;
    color: white;
}

</style>