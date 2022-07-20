<template>

    <div> 
        <label for="genre">Choose genre:</label>
        <select name="genre" id="genre" v-model="inputSelect">
            <option value="">All</option>
            <option value="Rock">Rock</option>
            <option value="Pop">Pop</option>
            <option value="Jazz">Jazz</option>
            <option value="Metal">Metal</option>
        </select>
        <button @click="$emit('search', inputSelect.value)">Filtra per genere</button>
    </div>

</template>

<script>
export default {
    name: 'GenreSelection',

}
</script>

<style>
label{
  color: white;
}
</style>