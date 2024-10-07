<script setup>


const filmes = reactive( [ 
  {
    id:0,
    nome:"Harry Potter",
     preco: 123.00,
     alugado: false,
  },

  {
    id:1,
    nome:"Capitão Fantastico",
    preco: 33.00,
    alugado: false,

   },

   {
    id:2,
    nome:"Efeito Borboleta",
    preco: 33.00,
    alugado: true,


   },


])


function alteraAlugado(id){
  filmes[id].alugado = true;

}


</script>


<template>

<Cabecalho/>

</hr>

<p><strong>Filmes recomendados:</strong></p>

<div class="conteudo">


  <Filme v-for="filme in filmes" v-bind:filme="filme" v-bind:alteraAlugado="alteraAlugado"/>

</div>
  
</template>

<style>
.conteudo{

  display:flex;
  gap: 20px;

}

</style>

