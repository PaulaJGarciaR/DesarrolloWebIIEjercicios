<script setup>
import { ref } from 'vue';
let ListaTareas=ref(['Estudiar Mantenimiento 2','Estudiar Calculo','Estudiar Electro'])
function Agregar(){
  let TareaNueva=document.getElementById("TareaNueva").value
  ListaTareas.value.push(TareaNueva)
}
function Eliminar(index){
  ListaTareas.value.splice(index,1)

}
</script>

<template>
  <div class="w-[30%] mx-auto font-Oswald bg-[#B4BEC9] mt-4 rounded pb-5">
    <h1 class="text-xl pt-2 text-center ">Tareas Pendientes</h1>
    <div class="w-[100%] flex flex-wrap justify-center mb-3">
      <div class="w-[80%] bg-white mt-4 rounded   " v-for="(ListaTareas,index) in ListaTareas" :key="index" @click="Eliminar(index)">
        <div class="flex justify-evenly">
          <h1 class="ml-2 w-[90%]">{{ ListaTareas }}</h1>
        <div class="px-2 bg-[#159A9C] w-[3%] rounded flex items-center justify-center">X</div></div>
      
      </div>
    </div>
     <div class="w-[100%] flex justify-evenly">
      <input class="w-[40%]" type="text" placeholder="Nueva Tarea" id="TareaNueva">
      <div class="w-[40%] bg-[#002333] rounded" @click="Agregar"><h1 class="text-center cursor-pointer text-white ">Agregar</h1></div>
     </div>
  </div>
</template>

