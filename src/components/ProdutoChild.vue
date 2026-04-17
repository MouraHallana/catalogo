<script setup>
defineProps(['nome', 'preco', 'categoria', 'id'])
defineEmits(['corrigirpreco'])
import ButtonChild from './ButtonChild.vue';
import IconDocumentation from './icons/IconDocumentation.vue';
import { formataPreco } from '@/utils/produtoUItils';
</script>
<template>
    <li>
        {{ nome }} -  {{ preco }} ({{ categoria }})
        <ButtonChild @clique="$emit('corrigirpreco', id, preco)">
            Corrigir Preço
        </ButtonChild>
    </li>
</template>
<style scoped>
</style>