<script setup>
// El padre le esta enviando información al hijo
const props=defineProps({
    tarea:{
        type:String,
        default:'Tarea Indefinida'
    },
    index:{
        type:Number
    }
})
// defineEmits=>cada posición del array es una señal
const emit=defineEmits(['borrarTarea'])
function borrarTarea(index){
    // console.log('borrarTarea',index);
    emit('borrarTarea',index)
}
</script>
<template>
<div class="flex justify-between bg-gray-200 rounded px-4 py-1 mt-4">
   {{ props.tarea }}
  <span class=" rounded bg-red-500  text-center text-white hover:cursor-pointer hover:bg-red-400 px-2 py-1" @click="borrarTarea(props.index)">x</span>
</div>
</template>