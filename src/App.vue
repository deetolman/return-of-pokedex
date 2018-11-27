<template>
  <div id="app">
    <Header/>
    <Pokedex v-bind:pokemons="pokemons"/>
  </div>
</template>

<script>
import Pokedex from './components/Pokedex.vue';
import pokemons from '../services/pokedex.js';
import Header from './components/Header.vue';

export default {
    data() {
        return {
            pokemons: pokemons.getPokemons()
        };
    },
    components: {
        Header,
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
