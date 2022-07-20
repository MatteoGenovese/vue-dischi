<template>

    <div>
        <label for="genre">Choose genre:</label>
        <select name="genre" id="genre" v-model="inputSelect" @change="$emit('search', inputSelect)">
            <option value="">All</option>
            <option value="Rock">Rock</option>
            <option value="Pop">Pop</option>
            <option value="Jazz">Jazz</option>
            <option value="Metal">Metal</option>
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
    }
    ,
    methods: {
        prova(needle) {
            console.log(inputSelect)
        }
    }

}
</script>

<style>
label {
    color: white;
}
</style>