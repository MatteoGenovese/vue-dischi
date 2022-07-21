<template>

    <div>
        <label for="genre">Choose genre:</label>
        <select name="genre" id="genre" v-model="inputSelect" @change="$emit('search', inputSelect)">
        <option
        v-for="(genre,index) in genreList"
        :key="index"
        :value="genre">{{genre}}</option>

        </select>

    </div>

</template>

<script>
export default {
    name: 'GenreSelection',
    data: function () {
        return {
            inputSelect: "",

        }
    },
    methods: {
        prova(needle) {
            console.log(inputSelect)
        }
    },
    props: {
        'genreList':Array,
    },

}
</script>

<style>
label {
    color: white;
}
</style>