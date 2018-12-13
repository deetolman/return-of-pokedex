<template>
<section v-if="pokemon">    
    <h1>{{pokemon.pokemon}}</h1>
    <p>
     <button @click="showModal = true">show detail</button>
    </p>
</section>
</template>

<script>
export default {
    data() {
        return {
            showModal: false
        };

    },
    props: {
        pokemon: Object
    } 
};   
</script>

<style>

</style>
