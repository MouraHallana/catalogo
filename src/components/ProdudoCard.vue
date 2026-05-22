<script setup>
import { formataPreco } from '@/utils/produtoUItils';
import ButtonChild from './ButtonChild.vue';
defineProps(['id', 'nome', 'preco', 'imagem', 'categoria'])
</script>
<template>
  <div class="produto-card">
    <div>
      <h2>{{ nome }}</h2>
      <p>Preçp: {{ formataPreco(preco) }}</p>
    </div>
    <div>
      <img :src="imagem" :alt="nome" class="produto-imagem" />
    </div>
    <ButtonChild>Editar</ButtonChild>
  </div>

</template>
<style scoped>
.produto-card {
  display: flex;
  align-items: center;
  justify-content: space-between;
  border: 1px solid #ccc;
  padding: 15px;
  margin-bottom: 15px;
  margin-top: 20px;
}

.produto-imagem {
  height: 100px;
  width: 100px;
  object-fit: cover;
}

h2 {
 font-weight: bold;
 margin-bottom: 16px;
}

button {
  border-radius: 20px;
  padding:5px 10px 5px 10px;
  background-color: antiquewhite;
}
</style>
