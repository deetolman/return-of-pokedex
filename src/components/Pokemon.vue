<template>
    <div>
    <li @click="handleSelect">
        <div class="info">
            <h2>Name: {{ pokemon.pokemon }}</h2>
            <h3>Weight: {{ pokemon.weight }}</h3>
            <h3>Type: {{ pokemon.type_1}}</h3>
            <h3>Defense: {{ pokemon.defense }}</h3>
            <img v-bind:src="pokemon.url_image"
            />
        </div>
    </li>
       <!-- <PokemonDetail :pokemon="pokemon"/> -->
    </div>
</template>

<script>
// import PokemonDetail from './PokemonDetail.vue';

export default {
    props: {
        pokemon: Object
    },
    methods: {
        handleSelect() {
            console.log(this.pokemon.pokemon);
        }
    }
};
</script>

<style>
img {
    width:150px;
}
li {
    border:solid 0.4px;
}
</style>
