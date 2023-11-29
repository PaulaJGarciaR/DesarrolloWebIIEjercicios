<script setup>
import TaskComponent from '@/components/TaskComponent.vue'
import { ref } from 'vue';
const tareas = ref(['Estudiar','Sacar 5','Descansar'])
function deleteTask(index){
// console.log('Borrar Hijo', index)
tareas.value.splice(index,1)
}
</script>

<template>
  <div class="bg-gray-50 w-96 shadow-md rounded mx-auto mt-12 px-4 py-3">
  <h1 class="text-2xl font-semibold text-center">Tareas</h1>
  <div class="flex">
  <input class="w-4/5 h-8 px-2 py-1 border rounded-sm border-green-600">
  <span class="w-1/5 h-8 text-xl rounded bg-green-700 text-white text-center hover:cursor-pointer hover:bg-green-400">+</span>
 </div>
<!-- Sintaxis para importar el componente  -->
<!-- <TaskComponent/>
 <TaskComponent></TaskComponent> -->
 <TaskComponent 
 v-for="(task, index) in tareas" 
 :key="index"
 :tarea="task"
 :index="index"
 @borrarTarea="deleteTask"
 />


 </div>
 
</template>


