<template>
  <div>

    <div class="container">
      <Card v-for="(card,index) in cards"
      :key="index"
      :element="card"
      />
    </div>

  </div>
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
      .then((result)=> {
        console.log(result.data.response);
        this.cards=result.data.response;
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
.card {
  height: 300px;
  width: calc(100% / 5);
  background-color: #fff;

  .img-container {
    width: 200px;
    height: 200px;
    object-fit: contain;
    overflow: hidden;
  }

  h2 {
    font-size: 1.5rem;
  }
}
</style>

