<template >
    <main>
        <CharacterSearchbar @searched="searchCharacters" />
        <CharactersList :charactersList="charactersList"/>
    </main>
</template>

<script>
import CharactersList from './CharactersList.vue';
import CharacterSearchbar from './CharacterSearchbar.vue';

import axios from 'axios';
import { store } from '../store.js';

export default {
    name:'AppMain',
    data(){
        return {
            store,
            charactersList: [],
            apiUrl: 'https://rickandmortyapi.com/api/character',
        }
    },
    components:{
        CharactersList,
        CharacterSearchbar
    },

    methods: {
        searchCharacters(needle = ''){
            axios.get(this.apiUrl, {
                    params: {
                        name: needle
                    }
                })
                .then( (response) => {

                    this.charactersList = response.data.results;
                    this.store.isLoading = false;

                })
                .catch(function (error) {
                    console.log(error);
                })
        }
    },


    created(){
        this.searchCharacters();
    }
}
</script>

<style lang="scss">

</style>