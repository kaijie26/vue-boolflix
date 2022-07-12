<!-- HTML -->
<template>
    <div class="container">
        <CardFilm />
        
    </div>

    
</template>

<!-- JAVASCRIPT -->
<script>
import CardFilm from './CardFilm.vue'
import axios from 'axios'

export default {
    name: 'MainComponent',
    components: {
        CardFilm,
    },

    props: {
        infoFilm: String

    },

    data(){
        return{
            arrayFilm:[],
            url: 'https://api.themoviedb.org/3/movie/550?api_key=553b5aa9ad4d3b90c09c3a4569be72aa',
            getResult: '',
        }

    },

    methods: {
        saveUserValue(){
            this.getResult = `${this.getResult}${this.infoFilm}`,

            axios.get(this.url).then((response) => {
            const myArray = response.data;
            this.arrayFilm.push(myArray)
           
        })

        }

    },

    created(){
        this.saveUserValue()
        
    }
    
}
</script>

<!-- CSS -->
<style lang="scss" scoped>

</style>