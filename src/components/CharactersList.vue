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
import { store } from '../store.js';


export default {
    name:'CharactersList',
    data(){
        return {
            store
        }
    },
    props:{
        charactersList : Array,
    },
    components:{
        CharacterCard,
        AnimatedLoader
    },

}
</script>

<style lang="scss">

</style>