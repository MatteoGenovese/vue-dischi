<template>
  
    <div class="card">
      <div class="img-container">
        <img src="https://img.discogs.com/vknPDdrqRbT92pNRX0W4I5N91jg=/fit-in/300x300/filters:strip_icc():format(jpeg):mode_rgb():quality(40)/discogs-images/R-1246953-1448927086-6590.jpeg.jpg" alt="">

      </div>
      <h2>{{card.year}}</h2>
      <h3>

        <!-- {{card.author}}
        <br>
        {{card.year}} -->

      </h3>
    </div>
  
</template>

<script>


export default {
  name: 'Card',
  props: [
    'card'
    ],
}
</script>


<style scoped lang="scss">

.card{
  height: 300px;
  padding: 10px;
  width: calc( 100% / 5);
  background-color: #2E3A46;
  display: flex;
  flex-direction: column;
  align-items: center;


  .img-container{
    width: 200px;
    height: 200px;
    
    overflow: hidden;
    text-align: center;
    img{
      width: 100%;
      object-fit: contain;
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

