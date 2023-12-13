<script setup>
import { ref } from 'vue';
let ArrayModuloUno=ref(["1-XDCHH","2-XTT550","3-XG3WQ"])
let ArrayModuloDos=ref(["1-WW99","2-WJKPL"])
let ArrayModuloTres=ref(["1-LOJ7","2-LNMKI","3-LGHJK"])
let CantidadTurnos=ref((ArrayModuloUno.value.length)+(ArrayModuloDos.value.length)+(ArrayModuloTres.value.length))
function agregarTurno(){
  let CodigoTurno=document.getElementById("CodigoTurno").value;
  let modulo=document.getElementById("modulo").value;
  if(modulo==1){
   ArrayModuloUno.value.push(CodigoTurno);
  }
  if(modulo==2){
   ArrayModuloDos.value.push(CodigoTurno);
  }
  if(modulo==3){
   ArrayModuloTres.value.push(CodigoTurno);
  }
  
  CantidadTurnos.value+=1;
}


</script>

<template>
   <div class="w-[80%] bg-slate-100 my-0 mx-auto mt-4 font-Oswald pb-5 rounded">
    <h1 class="text-center text-2xl pt-5">Sistema de Turnos</h1>
    <div class="w-[100%] flex justify-evenly rounded mt-7  ">
      <div class="w-[30%] pb-4 h-auto">
        <div class="w-[100%] bg-blue-500 py-4 rounded rounded-b-none "><h1 class="text-center text-white">MÓDULO 1</h1></div>
        <div class="w-[100%] bg-slate-200 flex flex-wrap justify-center pb-3">
          <div class="w-[80%] bg-white mt-4" v-for="(ArrayModuloUno,index) in ArrayModuloUno" :key="index">
            {{  ArrayModuloUno }}</div>
        </div>
      </div>
      <div class="w-[30%] h-auto ">
        <div class="w-[100%] bg-amber-400 py-4 rounded rounded-b-none "><h1 class="text-center text-white">MÓDULO 2</h1></div>
        <div class="w-[100%] bg-slate-200 h-auto flex flex-wrap justify-center pb-3">
          <div class="w-[80%] bg-white mt-4" v-for="(ArrayModuloDos,index) in ArrayModuloDos" :key="index">
            {{  ArrayModuloDos }}</div>
        </div>
      </div>
      <div class="w-[30%]">
        <div class="w-[100%] bg-green-600 py-4 rounded rounded-b-none "><h1 class="text-center text-white">MÓDULO 3</h1></div>
        <div class="w-[100%] bg-slate-200 h-auto flex flex-wrap justify-center pb-3">
          <div class="w-[80%] bg-white mt-4" v-for="(ArrayModuloTres,index) in ArrayModuloTres" :key="index">
            {{  ArrayModuloTres }}</div>
        </div>
      </div>
    </div>
   </div>
   <div class="w-[80%] bg-slate-100 mt-2 mx-auto font-Oswald py-4 rounded">
    <div class="w-[100%] flex justify-evenly">
    <div class="w-[20%] flex">
    <h1 class="w-[15%] text-2xl">{{ CantidadTurnos }}</h1>
    <h1 class="w-[85%] ">TURNOS</h1>
  </div>
    <input type="text" placeholder="Ingresar codigo" class="border border-slate-300 w-[20%]" id="CodigoTurno">
    <select name="Modulo" id="modulo" class="w-[20%] border border-slate-300" >
      <option value="1">Modulo 1</option>
      <option value="2">Modulo 2</option>
      <option value="3">Modulo 3</option>
    </select>
     <div class="w-[20%] py-2 px-4 bg-purple-500 text-white text-center rounded cursor-pointer" @click="agregarTurno" ><h1>Agregar Turno</h1></div>
   </div>
  </div>
</template>



