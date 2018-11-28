<template>
    <li>
        <div class="info">
            <h2>{{ pokemon.pokemon }}</h2>
            <p>{{ pokemon.weight }}</p>
            <p>{{ pokemon.url_image }}</p>
            <!-- <img v-bind:src="" -->
        </div>
    </li>
</template>

<script>
export default {
    props: {
        pokemon: Object
    }
};
</script>

<style>

</style>
