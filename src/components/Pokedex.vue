<template>
    <ul>
        <Pokemon v-for="pokemon in pokemons"
        v-bind:key="pokemon.pokemon"
        v-bind:pokemon="pokemon"
        v-bind:selected="selected"
        />
    </ul>
</template>

<script>
import Pokemon from './Pokemon.vue';

export default {
    data() {
        return {
            selected: null
        };
    },
    props: {
        pokemons: Array
    },
    components: {
        Pokemon
    },
        
};

</script>

<style>
ul {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
    list-style-type: none;
    margin: 0;
    padding: 0;
}

</style>
