<template >
    <div class="container">
        <div class="row"  v-if="store.isLoading">
            <div class="col-12">
                <AnimatedLoader />
            </div>
        </div>
        <div class="row py-3 px-5 justify-content-evenly" v-else>
            <CharacterCard v-for="character in charactersList"
                :name="character.name"
                :species="character.species"
                :status="character.status"
                :image="character.image"
            />
        </div>
    </div>
</template>

<script>
import CharacterCard from './CharacterCard.vue';
import AnimatedLoader from './AnimatedLoader.vue';
import axios from 'axios';
import { store } from '../store.js';

export default {
    name:'CharactersList',
    data(){
        return {
            charactersList : [],
            store
        }
    },
    components:{
        CharacterCard,
        AnimatedLoader
    },

    created(){
        axios.get('https://rickandmortyapi.com/api/character')
        .then( (response) => {
            console.log(response.data.results);
            setTimeout( () => {
                this.charactersList = response.data.results;
                this.store.isLoading = false;
            }, 5000);
        })
        .catch(function (error) {
            console.log(error);
        })
    }
}
</script>

<style lang="scss">

</style>