<script setup>

import axios from "axios";

let dados = ref();
let digitado = ref(""); //projeto cadastro

async function buscaTodos(){
     let resposta = await axios.get ("https://pokeapi.co/api/v2/pokemon/bulbasaur")
     console.log( resposta );

     dados.value = resposta.data;


}

 async function pesquisar(){
    let resposta = await axios.get ("https://pokeapi.co/api/v2/pokemon/"+digitado.value)
     console.log( resposta );

     dados.value = resposta.data;


}


onMounted( () => {
    
    buscaTodos();
})

</script>

<template>

    <h1>Consulta na API do Pokémon</h1>

    <input v-model="digitado" placeholder="Digite o nome de um Pokémon" size="30" /> //projeto tbm
    <button v-on:click="pesquisar()">Pesquisar</button>

  <div v-if="dados !=null">

<strong> <p> {{dados.name}} </p> </strong>

<p> ID: {{dados.id}} </p>
<p> Habildade: {{dados.abilities[0].ability.name}} </p>

<img v-bind:src="dados.sprites.front_default"/>


  </div>

</template>