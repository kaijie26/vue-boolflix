<!-- HTML -->
<template>
        <!-- Single Film and SerieTv -->
        <li class="card" >
            <div class="cover">
                <!-- Poster -->
                <div class="poster-container">
                    <img v-if="item.poster_path" class="poster" :src="`https://image.tmdb.org/t/p/w342/${item.poster_path}`" alt="">
                    <img v-else class="poster" src="https://upload.wikimedia.org/wikipedia/commons/thumb/6/65/No-Image-Placeholder.svg/1665px-No-Image-Placeholder.svg.png" alt="">
                </div>

                <!-- Info-Container -->
                <div class="info-container">
                    <!-- Title -->
                    <div>
                        Titolo:{{ item.title? item.title : item.name }}
                    </div>

                    <!-- Original-Title -->
                    <div>
                        Titolo Originale:{{ item.original_title? item.original_title : item.original_name }}
                    </div>

                    <!-- Language -->
                    <div>Lingua:
                        <img v-if="flags.includes(item.original_language)" :src="require(`../assets/img/flag-${item.original_language}.png`)" class="flags" :alt="item.original_language" >
                        <span v-else>{{ item.original_language }}</span> 
                        
                    </div>

                    <!-- Vote -->
                    <div>
                        Voto:{{ item.vote_average }}
                        <span class="colored-star">
                            <i v-for="n in getStar(item.vote_average)" :key="n" class="fa-solid fa-star"></i>
                        </span>
                        <span class="empty-star">
                            <i v-for="n in 5 - getStar(item.vote_average)" :key="n" class="fa-regular fa-star"></i>
                        </span>
                    </div>

                    <!-- OverView -->
                    <div>
                        OverView:{{item.overview}}
                    </div>

                </div>

            </div>
            
        </li>

</template>


<!-- JAVASCRIPT -->
<script>
export default {
    name: 'CardFilm',
    props: {
        "item": Object
    },
    data(){
        return{
            flags: ['it', 'en', 'fr'],
            
        }
    },

    methods: {
        getStar(vote){
            
            return Math.round(vote / 2)
            

        }



    },

    created(){

    }
    
}
</script>
<!-- CSS -->

<style lang="scss" scoped>
.card{
    max-width: 250px;
    margin: 30px;
    font-size: 13px;
    color: white;
    
}

.flags{
    width: 30px;
}

.poster{
    height: 300px;
    object-fit: cover;
}

.colored-star{
    color: yellow;
    
}

.cover{
    position: relative;
}

.info-container{
    position: absolute;
    bottom: 0%;
    left: 0;
    width: 100%;
    height: 100%;
    overflow-x: auto;
    background: black;
    line-height: 20px;
    padding: 10px;
    display: none;
}

.cover:hover .info-container{
    display: block;
}

</style>