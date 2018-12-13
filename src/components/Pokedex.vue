<template>
<section>
       <transition name=bounce>
        <Modal v-if="showModal" 
        :onClose="() => showModal = false" id="modal">
        <PokemonDetail :pokemon="selected"/>
        </Modal>
       </transition>  

        <Pokemon v-for="pokemon in pokemons"
        v-bind:key="pokemon.pokemon"
        v-bind:pokemon="pokemon"
        v-bind:onSelect="handleSelect"/>
        
</section>
</template>

<script>
import Pokemon from './Pokemon.vue';
import PokemonDetail from './PokemonDetail';
import Modal from './Modal';

export default {
    data() {
        return {
            selected: null,
            showModal: false
        };
    },
    props: {
        pokemons: Array
    },
    components: {
        Pokemon,
        PokemonDetail,
        Modal
    },
    methods: {
        handleSelect(pokemon) {
            this.selected = pokemon;
            this.showModal = true;
        },
        
    }   
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
@keyframes bounce-in {
  0% {
    transform: scale(0);
  }
  50% {
    transform: scale(1.5);
  }
  100% {
    transform: scale(1);
  }
}

</style>
