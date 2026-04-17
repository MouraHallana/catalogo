<script setup>

import ProdutoChild from './components/ProdutoChild.vue';
import { ref } from 'vue'
import SalvarButtonChild from './components/SalvarButtonChild.vue';
import { listaProdutos } from './data/produtos';
import { formataPreco } from './utils/produtoUItils';
const produtos = ref(listaProdutos)

const preco = ref(0);
const posicaoProduto = ref(-1);
const alterando = ref(false);

function corrigirPreco (idProduto, precoProduto) {
    preco.value = precoProduto;
    posicaoProduto.value = produtos.value.findIndex(p => p.id === idProduto);
    alterando.value = true;
}

function salvarPreco () {
    produtos.value[posicaoProduto.value].preco = preco.value
    alterando.value = false;
}

</script>

<template>
    <div class="container">
        <h1>
            Catalógo de Produtos
        </h1>
        <div>
            <ul>
                <ProdutoChild v-for="produto in produtos" :key="produto.id" :categoria="produto.categoria" :nome="produto.nome" :preco="formataPreco(produto.preco)" :id="produto.id"
                @corrigirpreco="corrigirPreco" >
                 
                </ProdutoChild>
            </ul>
        </div>
        <div v-show="alterando">
             <label>Preço</label>
          <input type="text" v-model="preco">
           <!-- <button @click.prevent="salvarPreco()">Salvar</button> -->
            <SalvarButtonChild @cliquesalvar="salvarPreco">
                Salvar
            </SalvarButtonChild>
        </div>
         
    </div>
 
</template>

<style scoped>

</style>
