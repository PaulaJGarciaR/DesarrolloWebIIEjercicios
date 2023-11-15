<script setup>
import { ref } from 'vue';
let listaProductos = ref([{ Nombre: "Arroz", Cantidad: 10, Valor: 4000, Vencimiento: 10, Mensaje: "" }]);
let mostrarListaProductos = ref([]);
console.log(listaProductos.value[0].Vencimiento);
    if ((listaProductos.value[0].Vencimiento > 0) && (listaProductos.value[0].Cantidad > 0)) {
      mostrarListaProductos.value.push(listaProductos.value[0]);
    }
    console.log(mostrarListaProductos.value[0]);
  
function validar() {
  let nombreProducto = document.getElementById("nombreProducto").value;
  console.log(nombreProducto);
let cantidadProducto = document.getElementById("cantidadProducto").value;
let valorProducto = document.getElementById("valorProducto").value;
let diasVencimiento = document.getElementById("diasVencimiento").value;
let arrayListaProductos = ref([{ Nombre: nombreProducto ,  Cantidad: cantidadProducto ,  Valor: valorProducto , Vencimiento: diasVencimiento,  Mensaje: "" }]);
  if (((parseInt(cantidadProducto)) > 0) && ((parseInt(diasVencimiento)) > 0)) {
  mostrarListaProductos.value.push(arrayListaProductos.value[0]);
  
}
let validarVencimiento=false;

for(let i=0;i<mostrarListaProductos.value.length;i++){
  if(mostrarListaProductos.value[i].Vencimiento < 5){
     validarVencimiento=true;
  }

  if(validarVencimiento){
    mostrarListaProductos.value[i].mensaje='EL PRODUCTO VENCERA PRONTO';
  }else{
    mostrarListaProductos.value[i].mensaje='';
  
  }
}
}
let validarVencimiento=false;

for(let i=0;i<mostrarListaProductos.value.length;i++){
  if(mostrarListaProductos.value[i].Vencimiento < 5){
     validarVencimiento=true;
  }

  if(validarVencimiento){
    mostrarListaProductos.value[i].mensaje='EL PRODUCTO VENCERA PRONTO';
  }else{
    mostrarListaProductos.value[i].mensaje='';
  }
}


</script>


<template>
  <div class="padre">
    <h1>Lista de Productos</h1>
    <div class="Ingreso-Productos">
      <h3>Ingresar Producto</h3>
      <label for="">Nombre Producto</label>
      <input type="text" id="nombreProducto">
      <label for=""> Cantidad</label>
      <input type="text" id="cantidadProducto">
      <label for="">Valor</label>
      <input type="text" id="valorProducto">
      <label for=""> Dias Vencimiento:</label>
      <input type="text" id="diasVencimiento">
      <div class="caja-boton">
        <button id="Agregar" @click="validar">Agregar</button>
      </div>
    </div>
    <div class="lista">
      <ul v-for="(mostrarListaProductos, index) in mostrarListaProductos" :key="index">
        <li>Nombre:{{ mostrarListaProductos.Nombre }}</li> 
        <p>{{ mostrarListaProductos.mensaje }}</p>
        <li>Cantidad:{{ mostrarListaProductos.Cantidad }}</li>
        <li>Valor:{{ mostrarListaProductos.Valor }}</li>
        <li>Dias Vencimiento:{{ mostrarListaProductos.Vencimiento }}</li>
      </ul>
    </div>
  </div>
</template>

<style scoped>
.Ingreso-Productos {
  width: 30%;
  display: flex;
  flex-direction: column;
  margin: 0 auto;
  text-align: center;
}

.caja-boton {
  padding: 10px 0;
}

#Agregar {
  border-style: none;
  background-color: #F1BA85;
  padding: 5px 10px;
  border-radius: 10px;

}

h1 {
  text-align: center;
}

.padre {
  background-color: #5B79A8;
  width: 50%;
  margin: 0 auto;
  padding-bottom: 20px;
  font-family: 'Oswald', sans-serif;
  border-radius: 10px;
  color: white;
}

.lista {
  width: 60%;
  flex-direction: column;
  display: flex;
  justify-content: center;
  background-color: #EEF0F4;
  margin-bottom: 10px;
  margin: 0 auto;
  border-radius: 10px;
  color: black;
}

input {
  border-style: none;
}
</style>
