<script setup>
import { ref } from 'vue';
let horaActualEntradaArray=[];
let horaActualEntrada=ref('');
function horaEntrada(){
  let momentoEntrada=new Date();
  let horaEntrada=momentoEntrada.getHours();
  let minitosEntrada=momentoEntrada.getMinutes();
  let segundosEntrada=momentoEntrada.getSeconds();
    horaActualEntrada.value=horaEntrada+":"+minitosEntrada+":"+segundosEntrada;
   horaActualEntradaArray=horaActualEntrada.value.split(":");
   console.log(horaActualEntradaArray);
}
let tiempoTranscurridoValor=ref('');
function tiempoTranscurrido(){
  let momentoActual=new Date();
let hora=momentoActual.getHours();
let minitos=momentoActual.getMinutes();
let segundos=momentoActual.getSeconds();
let horaActual=hora+":"+minitos+":"+segundos;
let horaActualArray=horaActual.split(":");
console.log(horaActualArray);
let horasTranscurridas=((parseInt(horaActualArray[0]))-(parseInt(horaActualEntradaArray[0])));
let minutosTranscurridos=((parseInt(horaActualArray[1]))-(parseInt(horaActualEntradaArray[1])));
let segundosTrascurridos=((parseInt(horaActualArray[2]))-(parseInt(horaActualEntradaArray[2])));
tiempoTranscurridoValor.value="Horas:"+horasTranscurridas+",Minutos:"+minutosTranscurridos+",segundos:"+ Math.abs( segundosTrascurridos);
console.log(tiempoTranscurridoValor);
}
let listaVehiculos=ref([]);
function ListaAuto(){
  let tipoVehiculo=document.getElementById("cajaTipoVehiculo").value;
let informacionVehiculo=ref([{Vehiculo:tipoVehiculo,Entrada:horaActualEntrada.value,tiempoTranscurridoParqueadero:tiempoTranscurridoValor.value,Salida:false}]);
listaVehiculos.value.push(informacionVehiculo.value[0]);
console.log(informacionVehiculo);
console.log(listaVehiculos.value.length);
}

</script>

<template>
   <h1>Lista Parqueadero</h1>
  <div class="padre">
    <div class="listaVehiculos">
      <div class="contenedorLista">
        <label for="">Tipo de Vehiculo</label>
      <input type="text" id="cajaTipoVehiculo">
      <label for="">Hora de Ingreso:</label>
      <label for="" id="cajaHoraIngreso">{{ horaActualEntrada }}</label>
      <button @click="horaEntrada">Registrar hora de Ingreso</button>
      <label for="">tiempoTranscurrido:</label>
      <label for="">{{ tiempoTranscurridoValor }}</label>
      <button @click="tiempoTranscurrido">Calcular tiempo Transcurrido</button>
      <button @click="ListaAuto">Lista informacion Auto</button>
      <ul v-for="(listaVehiculos,index) in listaVehiculos" :key="index">
        <li>{{ listaVehiculos.Vehiculo }}</li>
      </ul>
      </div>
  
    </div>
<!-- <button @click="horaEntrada">Enviar</button>
<button @click="tiempoTranscurrido">Calcular</button> -->

  </div>
</template>

<style scoped>
.padre{
  width: 100%;
  display: flex;
  font-family: 'Oswald', sans-serif;
}
.listaVehiculos{
  width: 40%;
  display: flex;
  flex-direction: column;
  background-color: #F2C9DC;
  border-radius: 20px;
  flex-wrap: wrap;
  margin:0 auto;
}
.contenedorLista{
  width: 30%;
  margin:0 auto;
  padding: 10px 0;
  display: flex;
  flex-direction: column;
}
button{
  font-family: 'Oswald', sans-serif;
  border-style: none;
  border-radius: 10px;
  width: 100%;
  margin: 10px 0;
}
input{
  border-style: none;
}
h1{
  font-family: 'Oswald', sans-serif;
  text-align: center;
}
</style>
