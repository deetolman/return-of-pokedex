<template>
<section v-if="pokemon"> 
    <p>DETAILS:</p>   
    <h1>{{pokemon.pokemon}}</h1>
      <h3>Weight: {{ pokemon.weight }}</h3>
      <h3>Type: {{ pokemon.type_1}}</h3>
      <h3>Defense: {{ pokemon.defense }}</h3>
</section>
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
