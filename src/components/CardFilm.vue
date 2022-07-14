<!-- HTML -->
<template>
        <!-- Single Film and SerieTv -->
        <li class="card" >
            <div>
                Titolo:{{ item.title? item.title : item.name }}
            </div>
            <div>
                Titolo Originale:{{ item.original_title? item.original_title : item.original_name }}
            </div>
            <div>Lingua:
                <img v-if="flags.includes(item.original_language)" :src="require(`../assets/img/flag-${item.original_language}.png`)" class="flags" :alt="item.original_language" >
                <span v-else>{{ item.original_language }}</span> 
                
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
            flags: ['it', 'en', 'fr']
            
            
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

.flags{
    width: 70px;
}

</style>