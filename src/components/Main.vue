<template>
  <main>
    <div class="container">
      <CardList />
    </div>

  </main>
</template>

<script>
import CardList from './CardList.vue'

export default {
  name: 'Main',
  components: {
    CardList,
  }
}
</script>


<style scoped lang="scss">
main {
  height: 90vh;
  background: #1E2C3B;
}
</style>

