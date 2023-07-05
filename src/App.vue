<script setup>
import { questoes } from '@/_data/pergunta.js'
function verificar(resposta) {
  if (resposta.correta == true) {
    console.log(resposta)
    alert("correto")
  } else {
    console.log(resposta)
    alert("errado")
  }
}

function dica(questao){
 alert(questao.dica)
}
</script>
<template>
  
  <div class="card " >
  
        
    
    <hr>
    <div v-for=" (questao, index) in questoes">

      <h3 class="card-title" style="display: flex;justify-content: center;">Questao {{ questao.id }}</h3>
            <p class="card-text"> {{ questao.pergunta }} </p>
            <button class="dica" @click="dica(questao)">Dica</button>
            
            <div class="botao" @click="verificar(resposta)" v-for="(resposta, i) in questao.respostas">
              {{ resposta.texto }}
              
            </div>
            <hr>
          </div>
          </div>
        
</template>
<style>
 



.card{
  width: 60rem; 
  min-height: calc(100% - 300px);
  background-color: rgba(100, 148, 237, 0.705);
  padding: 5%;
  border-radius: 5px;
}
.card-text , .card-title{
  color: aliceblue;
}
  .botao{
  padding: 3%;
  border: 1px solid black;
  background-color: rgb(225, 246, 255);
cursor: pointer;
  border-radius: 10px;
  margin-bottom: 10px;

}
.botao:hover{
  background-color: rgba(225, 246, 255, 0.678);
  padding: 25px;
}

</style>