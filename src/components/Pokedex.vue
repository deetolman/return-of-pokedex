<template>
    <ul>
        <Pokemon />
    </ul>
</template>

<script>
import Pokemon from './Pokemon.vue';
export default {
    props: {
        pokedex: Array
    },
    components: {
        Pokemon
    }
};
</script>

<style>

</style>
