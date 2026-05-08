<script setup>
import { ref } from 'vue';
import { listaProdutos } from '@/data/produtos';
import { formataPreco } from '@/utils/produtoUItils';


const produtos = ref(listaProdutos);

produtos.value = produtos.value.filter(p => p.categoria === 'Brinquedos');

</script>
<template>

<div class="container">

<div class="produtos">

  <div v-for="produto in produtos" :key="produto.id" class="produto-car">

 <img :src="produto.imagem" :alt="produto.nome" class="produto-imagem">
<h2>{{ produto.nome }}</h2>
<p>
        Preço: {{ formataPreco(produto.preco) }}
      </p>

  </div>

</div>

</div>





</template>
<style scoped>
</style>
