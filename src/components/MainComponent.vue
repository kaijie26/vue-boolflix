<!-- HTML -->
<template>
    <div class="container">
        <div>
            Titolo:[title]
        </div>
        <div>
            Titolo Originale:[original title]
        </div>
        <div>
            Lingua:[language]
        </div>
        <div>
            Voto:[vote]
        </div>
        
        
    </div>

    
</template>

<!-- JAVASCRIPT -->
<script>
import axios from 'axios'

export default {
    name: 'MainComponent',

    data(){
        return{
            arrayFilm:[],
            url: 'https://api.themoviedb.org/3/movie/550?api_key=553b5aa9ad4d3b90c09c3a4569be72aa'
        }

    },

    mounted(){
        axios.get(this.url).then((response) => {
            console.log(response.data);

        })
    }
    
}
</script>

<!-- CSS -->
<style lang="scss" scoped>

</style>