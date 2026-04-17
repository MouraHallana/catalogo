<script setup>
defineEmits(['cliquesalvar'])
</script>
<template>

    <button @click.prevent="$emit('cliquesalvar')">
        <slot>

        </slot>
    </button>

</template>
<style scoped>
button {
    background-color: chartreuse;
    color: rgb(77, 107, 47);
    border-radius: 18px;
    margin: 5px;
    border: 2px solid rgb(109, 177, 40);
    padding: 5px 10px 5px 10px;
}
</style>
