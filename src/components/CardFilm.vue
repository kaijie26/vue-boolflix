<!-- HTML -->
<template>
    <div>
        <ul>
            <li v-for="(film, index) in arrayFilm" :key="index" :infoFilm="film" class="card" >
                <div>
                    Titolo:{{ infoFilm.title }}
                </div>
                <div>
                    Titolo Originale:{{ infoFilm.original_title }}
                </div>
                <div>
                    Lingua:{{ infoFilm.spoken_languages }}
                </div>
                <div>
                    Voto:{{ infoFilm.vote_count }}
                </div>

            </li>

        </ul>

    </div>

</template>


<!-- JAVASCRIPT -->
<script>
export default {
    name: 'CardFilm',
    props: {
        infoFilm: String
    },
    data(){
        return{
            arrayFilm: []
        }
    }
    
}
</script>
<!-- CSS -->

<style lang="scss" scoped>

</style>