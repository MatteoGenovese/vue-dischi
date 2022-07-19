<template>
  <div>

    <div class="container">
      <Card />
    </div>

  </div>
</template>

<script>

import Card from './Card.vue'

export default {
  name: 'CardList',
    components: {
    Card,
  }
}
</script>


<style scoped lang="scss">

.card{
  height: 300px;
  width: calc( 100% / 5);
  background-color: #fff;
  .img-container{
    width: 200px;
    height: 200px;
    object-fit: contain;
    overflow: hidden;
  }
  h2{
    font-size: 1.5rem;
  }
}

</style>

