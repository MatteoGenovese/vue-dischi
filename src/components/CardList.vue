<template>
  <section>

    <div class="container">
      <GenreSelection @search="searchAlbum" :genreList="genreList"/>

      <!-- v-for="(genre,index) in genreList"
      :key="index"
      :genre="genre" -->
    </div>



    <div class="container d-flex flex-wrap p-5 card-container">
      <Card v-for="(card, index) in cardsFiltered" :key="index" :card="card" />
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
      dataStoraged: false,
      cards: [],
      cardsFiltered: [],
      genreList: [],

    }
  },
  methods: {
    getCards() {
      axios.get('https://flynn.boolean.careers/exercises/api/array/music')
        .then((result) => {
          console.log(result.data.response);
          this.cards = result.data.response;
          this.cardsFiltered = result.data.response; //agisco sempre sull'array copiato per la visualizzazione
          this.dataStoraged == true;
          this.searchGenreToDisplay();
        })
        .catch((error) => {
          console.warn(error);
        })
    },
    searchAlbum(needle) {
      if (needle == 'All') {
        this.cardsFiltered = [...this.cards]
      }
      else {
        this.cardsFiltered = this.cards.filter((element) => {
          return element.genre == needle
        });
      }
    },
    searchGenreToDisplay(){
      this.genreList.push('All')
        this.cards.forEach(element => {
          if(!(this.genreList.includes(element.genre)))
            this.genreList.push(element.genre)
        });

        console.log(this.genreList)
    }
  }
  ,
  created() {
    this.getCards();

  }
}
</script>


<style scoped lang="scss">
.card-container {
  row-gap: 14px;
  gap: 15px;
}
</style>

