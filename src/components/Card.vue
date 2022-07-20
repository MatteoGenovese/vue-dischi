<template>
  
    <div class="card">
      <div class="img-container">
        <img :src="cPoster" alt="">

      </div>
      <h2>{{cTitle}}</h2>
      <h3>
        {{cAuthor}}
        <br>
        {{cYear}} 

      </h3>
    </div>
  
</template>

<script>


export default {
  name: 'Card',
  props: {
      cPoster : String,
      cTitle : String,
      cAuthor : String,
      cGenre : String,
      cYear : String,
  }
}
</script>


<style scoped lang="scss">

.card{
  height: 335px;
  padding: 10px;
  width: calc( ( 100% / 5 ) - 15px );
  background-color: #2E3A46;
  display: flex;
  flex-direction: column;
  align-items: center;


  .img-container{
    width: 155px;
    height: 155px;
    
    overflow: hidden;
    text-align: center;
    img{
      height: 100%;
      object-fit: cover;
    }
  }
  h2{
    font-size: 1.5rem;
    color: white;
    text-align: center;
  }
  h3{
    color:#797D77;
    font-size: 1rem;
    text-align: center;
  }
}

</style>

