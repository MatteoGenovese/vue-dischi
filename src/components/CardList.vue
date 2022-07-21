<template>
  <section>

    <div class="container">
      <GenreSelection @search="searchAlbum" />
    </div>



    <div class="container d-flex flex-wrap p-5 card-container">
      <Card
        v-for="(card, index) in cardsFiltered"
        :key="index"
        :card="card"
        />
    </div>


  </section>
</template>

<script>

import Card from './Card.vue';
import axios from 'axios';
import GenreSelection from './GenreSelection.vue';


export default {
  name: 'CardList',
  components: {
    Card,
    GenreSelection,
  },
  data: function () {
    return {
      cards: [],
      cardsFiltered:[],
    }
  },
  methods: {
    getCard() {

      axios.get('https://flynn.boolean.careers/exercises/api/array/music')
        .then((result) => {
          console.log(result.data.response);
          this.cards = result.data.response;
          this.cardsFiltered = result.data.response; //

        })
        .catch((error) => {
          console.warn(error);
        })
    },
    searchAlbum(needle){
      if (needle=='All'){
        this.cardsFiltered = [...this.cards]
      }
      else{
        console.log(needle)
        this.cardsFiltered = this.cards.filter( (element) => {
        console.log(element.genre, needle)
        return element.genre == needle});
      }
      
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

</style>

