<template >
    <div class="container">
        <div class="row justify-content-center">
            <div class="input-group mt-3 mb-4 w-75 ">
                <span class="input-group-text" id="basic-addon1">Search a character</span>
                <input type="text" class="form-control" placeholder="Character name" aria-label="Character name" aria-describedby="basic-addon1"  v-model="searchedText"

                @keyup.enter="$emit('searched', searchedText)">
            </div>
        </div>
    </div>
</template>

<script>
export default {
    name: 'CharacterSearchbar',
    data() {
        return {
            searchedText : ''
        }
    },
    methods: {
        logContent(content){
            console.log(content);
        }
    },
}
</script>

<style lang="scss" scoped>

</style>