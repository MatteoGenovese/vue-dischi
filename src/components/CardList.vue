<template>
  <section>
    <div class="container">
      <label for="genre">Choose genre:</label>
      <select name="genre" id="genre">
        <option value="" >All</option>
        <option value="Rock" >Rock</option>
        <option value="Pop" >Pop</option>
        <option value="Jazz" >Jazz</option>
        <option value="Metal" >Metal</option>
      </select>
    </div>



    <div class="container d-flex flex-wrap p-5 card-container">
      <Card v-for="(card, index) in cards" :key="index" :cPoster="card.poster" :cTitle="card.title"
        :cAuthor="card.author" :cGenre="card.genre" :cYear="card.year" />
    </div>


  </section>
</template>

<script>

import Card from './Card.vue';
import axios from 'axios';


export default {
  name: 'CardList',
  components: {
    Card,
  },
  data: function () {
    return {
      cards: [],
    }
  },
  methods: {
    getCard() {


      axios.get('https://flynn.boolean.careers/exercises/api/array/music')
        .then((result) => {
          console.log(result.data.response);
          this.cards = result.data.response;
        })
        .catch((error) => {
          console.warn(error);
        })



    }
  }
  ,
  created() {
    this.getCard();
  }
}
</script>


<style scoped lang="scss">
.card-container {
  row-gap: 14px;
  gap: 15px;
}
label{
  color: white;
}
</style>

