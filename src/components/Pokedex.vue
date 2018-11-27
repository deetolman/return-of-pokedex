<template>
    <ul>
        <h2>{{pokemons}}</h2>
        <Pokemon/>
    </ul>
</template>

<script>
import Pokemon from './Pokemon.vue';
export default {
    props: {
        pokemons: Array
    },
    components: {
        Pokemon
    }
};
</script>

<style>

</style>
