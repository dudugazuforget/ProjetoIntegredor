<script setup>
import { ref } from 'vue'

const MostrarAjuda = ref(false)
const MostraBoard = ref(true)


function AjudaMst() {
  MostrarAjuda.value = true

  if (MostrarAjuda.value = true) {
    MostraBoard.value = false
  }

}

function BoardMst(){
  MostraBoard.value = true
  
  if(MostraBoard.value = true){
    MostrarAjuda.value = false
  }
}
</script>

<template>
  <div v-if="MostraBoard" class="bord">
    <div class="pergunta">
 
    </div>
    <div class="resposta">

    </div>
    <button @click="" class="proximo">Proximo</button>
    <button @click="AjudaMst" class="ajuda">?</button>
  </div>


  <div class="ajudaBoard" v-if="MostrarAjuda">
    <button @click="BoardMst" class="X">Voltar</button>
  
  <div class="textAjuda"></div>
  </div>

</template>

<style scoped>
@import url('https://fonts.cdnfonts.com/css/oleo-script');

.bord {
  position: absolute;
  width: 800px;
  height: 609px;
  left: 300px;
  top: 30PX;
  background: #6294B0;


}

.proximo {
  position: absolute;
  width: 227px;
  height: 50px;
  background: rgba(56, 101, 111, 0.5);
  top: 520px;
  left: 270px;
  border: 0;
  color: aliceblue;
  cursor: pointer;

  font-family: 'Oleo Script';
  font-style: normal;
  font-weight: 400;
  font-size: 24px;

}

.proximo:hover {
  background: rgba(19, 34, 37, 0.5);
}

.ajuda {
  position: absolute;
  width: 50px;
  height: 50px;
  left: 740px;
  top: 550px;
  border-radius: 50%;
  border: 0;
  background: rgba(56, 101, 111, 0.5);
  cursor: pointer;
  color: aliceblue;


  font-family: 'Oleo Script';
  font-style: normal;
  font-weight: 400;
  font-size: 24px;
}

.ajuda:hover {
  background: rgba(19, 34, 37, 0.5);
}

.pergunta {
  position: absolute;
  width: 686px;
  height: 152px;
  top: 30px;
  left: 55px;
  background: rgba(56, 101, 111, 0.53);
  opacity: 0.7;
}

.resposta {
  position: absolute;
  width: 686px;
  height: 259px;
  left: 55px;
  top: 230px;
  background: rgba(56, 101, 111, 0.44);
}
.ajudaBoard{
  position: absolute;
  width: 500px;
  height: 600px;
  background: #6294B0;
  left: 400px;

  
}
.X{
  position: absolute;
  width: 100px;
  height: 50px;
  left: 200px;
  top: 10px;
  border-radius: 5%;
  border: 0;
  background: rgba(56, 101, 111, 0.5);
  cursor: pointer;
  color: aliceblue;


  font-family: 'Oleo Script';
  font-style: normal;
  font-weight: 400;
  font-size: 24px;
}

.X:hover{
  background: rgba(19, 34, 37, 0.5);
}
.textAjuda{
  position: absolute;
  width: 450px;
  height: 500px;
  background: rgba(56, 101, 111, 0.5);
  border-radius: 5px;
  top: 70px;
  left: 25px;
}
</style>

