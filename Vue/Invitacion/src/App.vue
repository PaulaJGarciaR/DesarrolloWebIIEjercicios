<script setup>
import { ref } from 'vue';
let nombre=ref("");
let apellido=ref("");
let telefono=ref("");
let mensaje=ref("");
let fechaActual=new Date();
let anioActual=parseInt(fechaActual.getFullYear());
let mesActual=parseInt(fechaActual.getMonth())+1;
let diaActual=parseInt(fechaActual.getDate());
let edadActual=ref(0);
console.log(anioActual);
console.log(mesActual);
console.log(diaActual);
function edad(){
  let fechaNacimiento=document.getElementById("fechaNacimientoUsuario").value;
  let fechaUsuario=fechaNacimiento.split('-');
  edadActual.value=anioActual-(parseInt(fechaUsuario[0]));
  if(mesActual<(parseInt(fechaUsuario[1]))){
    edadActual.value--;
  }else{
    if(diaActual<(parseInt(fechaUsuario[2]))){
    edadActual.value--;
    }
  }

    if(edadActual.value>=18){
    mensaje.value="No necesita Acompañante";
  }else{
    if(edadActual.value<18){
    mensaje.value="Necesita Acompañante";}
  }
  
}


</script>

<template>
 <div class="padre">
  <div class="contenedor-hijos">
    <div class="hijo-uno">
      <div class="contenido-caja">
      <label for="">Ingrese su nombre</label>
      <input v-model="nombre" type="text">
      <label for="">Ingrese su Apellido</label>
      <input v-model="apellido" type="text">
      <label for="">Ingrese su fecha de nacimiento "aaaa-mm-dd"</label>
      <input id="fechaNacimientoUsuario" @blur="edad"  type="text">
      <label for="">Ingrese su telefono</label>
      <input v-model="telefono" type="text">

      </div>
      
    </div>
    <div class="hijo-dos">
      <div class="contenido-caja">
      <label for="">Su nombre es:</label>
      <label for="">{{ nombre }}</label>
      <label for="">Su Apellido es:</label>
      <label for="">{{ apellido }}</label>
      <label for="">Su edad es:"</label>
      <label for="">{{ edadActual }}</label>
      <label for="">{{ mensaje }}</label>
      <label for="">Ingrese su telefono</label>
      <label for="">{{telefono}}</label>

      </div>
    </div>
  </div>
 </div>
</template>

<style scoped>
.padre{
  background-color:#F2CA99;
  width: 100%;
  font-family: 'Oswald', sans-serif;
}
.contenedor-hijos{
  width: 100%;
  display: flex;
  justify-content: space-evenly;
  padding: 20px 0;
}
.hijo-uno{
  width: 35%;
  display: flex;
  background-color: #F28A2E;
  justify-content: center;
  align-items: center;
  text-align: center;
  border-radius: 10px;
}
.contenido-caja{
  width: 50%;
  display: flex;
  flex-direction: column;
  padding: 20px 0;
}
.hijo-dos{
  background-color: #63A69F;
  width: 35%;
  display: flex;
  justify-content: center;
  align-items: center;
  text-align: center;
  border-radius: 10px;
}
input{
  border-style: none;
}
label{
  padding: 5px 0;
}
 
</style>
