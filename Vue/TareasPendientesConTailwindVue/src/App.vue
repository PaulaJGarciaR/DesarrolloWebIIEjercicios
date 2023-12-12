<script setup>
import TaskComponent from '@/components/TaskComponent.vue';
</script>

<template>
  <div class="w-[30%] my-0 mx-auto bg-[#13678A] rounded mt-8 font-oswald pb-4">
    <h1 class=" text-5xl text-white text-center pt-4">Lista de Tareas</h1>
    <div class="flex w-[100%] justify-center mt-4 mb-4">
      <input class="" type="text" placeholder="Ingresar nueva tarea">
    </div>
     
   <TaskComponent/>
   <TaskComponent/>
   <TaskComponent/>
   <TaskComponent/>
    
  </div>
</template>


