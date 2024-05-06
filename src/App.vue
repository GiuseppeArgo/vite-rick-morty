<script>
import axios from 'axios';
import AppCard from './components/AppCard.vue';

export default {
  components: {
    AppCard
  },
  data() {
    return {
      character: [],
    }
  },
  created() {
    axios
    .get("https://rickandmortyapi.com/api/character")
    .then((resp) => {
      this.character = resp.data.results;
      console.log(this.character);
    })
  }
}
</script>

<template>
  <h1 class="text-center py-4">Rick and Morty App</h1>

  <AppCard />
</template>

<style scoped>

</style>
