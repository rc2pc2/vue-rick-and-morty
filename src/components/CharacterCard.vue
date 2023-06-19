<template >
    <article class="card mb-5 col-2 me-3 p-0">
        <img :src="image" class="w-100" :alt="name + ' image'">
        <div class="card-body text-center">
            <h5 class="card-title fw-bold">
                {{ name }}
            </h5>
            <p class="card-text">
                {{ species }} - <small class="text-muted"> {{ status }}</small>
            </p>
        </div>
    </article>
</template>
<script>
export default {
    name:'CharacterCard',
    data(){
        return {

        }
    },
    props:{
        name : String,
        species : String,
        status : String,
        image : String,
    }
}
</script>
<style lang="scss">
    article{
        box-shadow: rgba(0, 0, 0, 0.25) 0px 54px 55px, rgba(0, 0, 0, 0.12) 0px -12px 30px, rgba(0, 0, 0, 0.12) 0px 4px 6px, rgba(0, 0, 0, 0.17) 0px 12px 13px, rgba(0, 0, 0, 0.09) 0px -3px 5px;
    }
</style>