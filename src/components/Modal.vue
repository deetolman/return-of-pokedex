<template>
    <div class="content" @click.stop="">
        <button class="close" @click="onClose">x</button>
        <slot></slot>
    </div>
</template>

<script>
export default {
    props: {
        onClose: Function
    }
};
</script>

<style>

</style>
