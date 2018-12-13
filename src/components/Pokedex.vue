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
        beforeEnter: function(el) {
            el.style.opacity = 0;
        },
        enter: function(el, done) {
            /*eslint-disable-next-line*/
            Velocity(
                el, { opacity: 1, fontSize: '1em', height: '300px' },
                { complete: done }
            );
        },
        leave: function(el, done) {
            /*eslint-disable-next-line*/
                Velocity(
                el,
                { opacity: 0, height: 0 },
                { complete: done });
        
        }
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
.bounce-enter-active {
    animation: bounce-in .5s;
}
.bounce-leave-active {
    animation: bounce-in .5s reverse;
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
