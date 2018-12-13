<template>
    <li v-on:click="onSelect(pokemon)">
        <div class="info">
            <h2>Name: {{ pokemon.pokemon }}</h2>
            <img v-bind:src="pokemon.url_image"
            />
        </div>
    </li>
</template>

<script>
export default {
    props: {
        pokemon: Object,
        onSelect: Function
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
