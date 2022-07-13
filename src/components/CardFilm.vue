<!-- HTML -->
<template>
        <!-- Single Film -->
        <li class="card" >
            <div>
                Titolo:{{ item.title }}
            </div>
            <div>
                Titolo Originale:{{ item.original_title }}
            </div>
            <div>
                Lingua:{{ item.spoken_languages }}
            </div>
            <div>
                Voto:{{ item.vote_count }}
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
            
            
        }
    },

    computed: {
        
    },

    methods: {

    },

    created(){

    }
    
}
</script>
<!-- CSS -->

<style lang="scss" scoped>
li{
    background-color: coral;
    margin: 10px;
}

</style>