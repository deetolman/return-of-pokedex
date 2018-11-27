<template>
  <div id="app">
    <Header/>
    <Pokedex/>
  </div>
</template>

<script>
import Pokedex from './components/Pokedex.vue';
import pokemonApi from '../services/pokedex.js';

export default {
    data() {
        return {
            pokedex: pokemonApi.getPokedex()
        };
    },
    components: {
        Pokedex
    }
};
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
