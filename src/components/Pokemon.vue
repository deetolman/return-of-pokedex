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
         <Modal v-if="showModal" :onClose="() => showModal = false" :pokemon="pokemon">
        <PokemonDetail :pokemon="selected"/>
        </Modal>
    </div>
</template>

<script>
import Modal from './Modal';

export default {
    data() {
        return {
            selected: null,
            showModal: false
        };
    },
    props: {
        pokemon: Object
    },
    methods: {
        handleSelect(pokemon) {
            this.selected = pokemon;
            this.showModal = true;    
        }
    },
    components: {
        Modal
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
