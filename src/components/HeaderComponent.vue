<!-- HTML -->
<template>
    <header>
        <!-- Logo -->
        <h1 class="logo">
            BOOLFLIX
        </h1>

        <!-- Search-area -->
        <div class="search-area">
            <input v-model="userSearch" @keyup.enter="saveUserValue()" type="text" placeholder="Ricerca un film">
            <button @click.prevent="saveUserValue()">Search</button>

        </div>
        
        
    </header>

</template>
<!-- JAVASCRIPT -->

<script>
export default {
    name:'HeaderComponent',

    data(){
        return{
            userSearch: '',
        }

    },

    methods:{
        saveUserValue(){
            this.$emit('searchedFilm', this.userSearch);
            this.userSearch = ''
        }

    }

    
}
</script>

<!-- CSS -->
<style lang="scss" scoped>

header{
    background-color: black;
    display: flex;
    justify-content: space-between;
    align-items: center;
    padding: 10px;
    

    .logo{
        color: red;
    }

    button{
        margin: 10px;

    }
}



</style>