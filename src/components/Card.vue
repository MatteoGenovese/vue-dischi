<template>
  <div>
    <div class="card">
      <div class="img-container">
        <img src="https://i.discogs.com/psDUUalbwHXuzNS7QgK93aG6ImE4JzALnOkCPtB1HVw/rs:fit/g:sm/q:40/h:300/w:300/czM6Ly9kaXNjb2dz/LWRhdGFiYXNlLWlt/YWdlcy9SLTEyNDY5/NTMtMTQ0ODkyNzA4/Ni02NTkwLmpwZWc.jpeg" alt="">
      </div>
      <h2>TITOLO ALBUM</h2>
      <h3>
        Artista
        <br>
        Anno
      </h3>
    </div>
  </div>
</template>

<script>
export default {
  name: 'Card',
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

