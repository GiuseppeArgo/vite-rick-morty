<script>
import axios from 'axios';

import AppCards from './components/AppCards.vue';
export default {
  components: {
    
    AppCards
  },
  data() {
    return {
      characters: [],
    }
  },
  created() {
    axios
    .get("https://rickandmortyapi.com/api/character")
    .then((resp) => {
      this.characters = resp.data.results;
      console.log(this.characters);
    })
  }
}
</script>

<template>
  <h1 class="text-center py-5">Rick and Morty App</h1>

  <AppCards :characters="characters"/>
</template>

<style lang="scss">
</style>