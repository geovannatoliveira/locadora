<script setup>

// Pega os parâmetros que foram passados
//const params = useAttrs(); // pega uma variavel apenas
const params = defineProps (["filme","alteraAlugado"]); // pega todo objeto





</script>



<template>

    <div class="conteudo">

        <p>{{ params.filme.nome }}</p>
        <p v-if="params.filme.alugado == true"><u>alugado</u> </p>
        <img src="https://placeholder.co/150"/>
        <p>R${{ params.filme.preco}}</p>
        <button v-on:click="params.alteraAlugado( params.filme.id )" v-if="params.filme.alugado == false" class="button1">Alugar</button>
        
    </div>
   

</template>

<style scoped>

.conteudo{
    display: flex;
    flex-direction: column;
    width: 200px;
    text-align: center;
    background-color: blueviolet;
    padding: 15px;
    color: #FFF;
    gap:10px;
    border-radius: 10px;

   

}

.button1{
        background-color: orange;
        color: #FFF;
        padding: 18px;
        border:none;

    }

</style>