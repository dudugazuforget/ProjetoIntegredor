<script setup>
import { questoes } from '@/_data/pergunta.js'
import { ref } from 'vue'

const total = questoes.length
const indice = ref(0)
const isDisable = ref(0)
const classButton = ref(0)
classButton.value = "botao"

function verificar(resposta) {
  isDisable.value = true
  if (resposta.correta == true) {
    console.log(resposta)
    $( "#resp1" ).addClass( ".green" );    
    alert("correto")
  } else {
    console.log(resposta)
    $( "#resp1" ).addClass( ".red" );    
    alert("errado")
  }
}

function dica(indice) {
  alert(questoes[indice.value].dica)
}
</script>

<template>
  <div class="card">

    <hr>
    <div>

      <h3 class="card-title" style="display: flex;justify-content: center;">Questao {{ questoes[indice].id }}</h3>
      <p class="card-text"> {{ questoes[indice].pergunta }} </p>
      <button class="dica" @click="dica(indice)">Dica</button>

      <button :id="'resp'+resposta.id" v-bind:disabled="isDisable" v-bind:class="classButton" @click="verificar(resposta)" v-for="(resposta, i) in questoes[indice].respostas">
        {{ resposta.texto }}
      </button>

      <button @click="indice--" :disabled="indice <= 0">Anterior</button>
      <button @click="indice++" :disabled="indice >= 14">Próxima</button>
      <hr>
    </div>
  </div>
</template>

<style>
.red { color: red; 
  background-color: brown;
}
.green { color: green; 
  background-color: brown;
}

.card {
  width: 60rem;
  min-height: calc(100% - 300px);
  background-color: rgba(100, 148, 237, 0.705);
  padding: 5%;
  border-radius: 5px;
}

.card-text,
.card-title {
  color: aliceblue;
}

.botao {
  padding: 3%;
  border: 1px solid black;
  background-color: rgb(225, 246, 255);
  cursor: pointer;
  border-radius: 10px;
  margin-bottom: 10px;

}

.botao:hover {
  background-color: rgba(225, 246, 255, 0.678);
  padding: 25px;
}
</style>