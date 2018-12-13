<template>
    <div class="modal" @click="onClose">
        <div class="content" @click.stop="">
            <button class="close" @click="onClose">x</button>
            <slot></slot>
        </div>
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
.modal {
  color:black; 
  position: fixed;
  top: 0; left: 0;
  height: 100%;
  width: 100%;
  display: flex;
  justify-content: center;
  align-items: center;
  background-color: gray;
  opacity: 0.9;
}

</style>
