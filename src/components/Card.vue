<template>
  
    <div class="card">
      <div class="img-container">
        <img :src="card.poster" alt="">
      </div>
      <h2>{{card.title}}</h2>
      <h3>
        {{card.author}}
        <br>
        {{card.year}} 
      </h3>
    </div>
  
</template>

<script>


export default {
  name: 'Card',
  props: {

    card:{
      poster : String,
      title : String,
      author : String,
      genre : String,
      year : String,
    },
      
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

