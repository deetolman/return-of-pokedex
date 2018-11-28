<template>
    <header>
        <label class="label">
            Type:
            <select v-model="filter.type_1">
                <option value="">All</option>
                <option 
                v-for="type_1 in types"
                v-bind:key="type_1"
                v-bind:value="type_1">
                {{type_1}}
                </option>
            </select>
        </label> 
        <label class="label">
            Weight:
            <input type="number" v-model.number="filter.weight" step="100">
        </label>
        <label class="label">
            Defense:
            <input type="number" v-model.number="filter.defense" step="100">
        </label>
    </header>
</template>

<script>
export default {
    props: {
        filter: Object,
        types: Array
    }
};
</script>

<style>
header {
    background: lightgoldenrodyellow;
    color: gray;
    padding: 20px;
}
.label {
    font-weight: 200px;
}
</style>
