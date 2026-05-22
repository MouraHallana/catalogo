<script setup>
import { ref } from 'vue'
import { listaProdutos } from '@/data/produtos';
import ProdudoCard from '@/components/ProdudoCard.vue';

const produtos = ref(listaProdutos);

produtos.value = produtos.value.filter(p => p.categoria === 'Alimentos');
</script>


<template>

  <div class="container">
    <h1>Alimentos</h1>
    <div class="produtos">
      <ProdudoCard v-for="produto in produtos" :key="produto.id" :nome="produto.nome" :preco="produto.preco" :categoria="produto.categoria"
      :imagem="produto.imagem">

      </ProdudoCard>
    </div>
  </div>

</template>

<style scoped>

</style>
