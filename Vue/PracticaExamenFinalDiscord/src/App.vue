<script setup>
import { ref } from 'vue';
let mensajesChat=ref([]);
let nombres=ref(["Natalia Cardenas","Paula Garcia","Ayelid Arevalo"])
let nombre=ref("")
let fechaActual=new Date();
let anioActual=fechaActual.getFullYear();
let mesActual=fechaActual.getMonth()+1;
let diaActual=fechaActual.getDate();
let fecha=diaActual+"/"+mesActual+"/"+anioActual
let hora=(fechaActual.getHours())+":"+(fechaActual.getMinutes());
function ChatNataliaCardenas(){
mensajesChat.value=["Holaaa","Como estas?","Una Pregunta"];
nombre.value=nombres.value[0];
}
function ChatPaulaGarcia(){
mensajesChat.value=["Holaaa Paula","Como estas Paula?","Una Pregunta Paula"];
nombre.value=nombres.value[1];
}
function ChatAyelidArevalo(){
mensajesChat.value=["Holaaa Aye","Como estas Aye?","Una Pregunta Aye"];
nombre.value=nombres.value[2];
}

</script>

<template>
  <div class="w-[90%] flex font-oswald mx-auto justify-center mt-12">
  <div class=" w-[4%] h-auto bg-slate-800 ">
    <div class=" w-[85%]  mt-4 mx-auto   ">
      <img class="rounded-full" src="https://img.freepik.com/vector-gratis/ilustracion-dibujos-animados-gallina-pollito_138676-2054.jpg" alt="">
    </div>
    <h1 class="text-white text-center">Perfil</h1>
  </div>
  <div class="w-[20%] bg-slate-700 ">
    <div class="text-gray-400 ml-5">
      <p class="mb-4 mt-7 text-xl">TENDENCIAS</p>
      <p class="mt-3">#Titanic</p>
      <p class="mt-3">#FinalSemestre:D</p>
      <p class="mt-3">#UFC</p>
      <p class="mt-3">#ColombiaMarcha</p>
      <p class="mt-3">#UFPSO</p>
    </div>
    <div class=" mt-7 text-gray-200 w-[100%]  pb-5 ">
      <h1 class="ml-5">MENSAJES DIRECTOS</h1>
      <div class="w-[90%] flex bg-slate-500 py-2 rounded mx-auto mt-2" @click="ChatNataliaCardenas">
        <img  class="w-12 h-12 rounded-full ml-5" src="https://static.vecteezy.com/system/resources/previews/005/845/877/non_2x/cute-cow-sitting-cartoon-icon-illustration-animal-icon-concept-isolated-premium-flat-cartoon-style-vector.jpg" alt="">
        <div class="ml-7">
          <h1 class="text-[15px]">Natalia Cardenas</h1>
          <h2 class="text-[12px]">Hace 10 minutos</h2>
        </div>
      </div>
      <div class="w-[90%] flex bg-slate-500 py-2 rounded  mx-auto mt-2" @click="ChatPaulaGarcia">
        <img  class="w-12 h-12 rounded-full ml-5" src="https://static.vecteezy.com/system/resources/previews/005/845/877/non_2x/cute-cow-sitting-cartoon-icon-illustration-animal-icon-concept-isolated-premium-flat-cartoon-style-vector.jpg" alt="">
        <div class="ml-7">
          <h1 class="text-[15px]">Paula Garcia</h1>
          <h2 class="text-[12px]">Hace 10 minutos</h2>
        </div>
      </div>
      <div class="w-[90%] flex bg-slate-500 py-2 rounded  mx-auto mt-2" @click="ChatAyelidArevalo">
        <img  class="w-12 h-12 rounded-full ml-5" src="https://static.vecteezy.com/system/resources/previews/005/845/877/non_2x/cute-cow-sitting-cartoon-icon-illustration-animal-icon-concept-isolated-premium-flat-cartoon-style-vector.jpg" alt="">
        <div class="ml-7">
          <h1 class="text-[15px]">Ayelid Arevalo</h1>
          <h2 class="text-[12px]">Hace 10 minutos</h2>
        </div>
      </div>
    </div>
  </div>
  <div class="w-[40%] bg-slate-600 ">
    <div class="w-[100%] flex justify-center flex-wrap">
      <h1 class="mt-5">{{ nombre }}</h1>
      <div class="w-[90%] h-auto bg-slate-500 border border-slate-200 mt-5 text-left"
     v-for="(mensajesChat,index) in mensajesChat" :key="index" >
      {{ mensajesChat }}
      <h1 class="text-[10px] text-right">{{ fecha }}</h1>
      <h1 class="text-[10px] text-right">{{ hora }}</h1>
      </div>

    </div>
  
  </div>
  <div class="w-[20%] bg-slate-700">
  <h1 class="ml-5 mt-5 text-gray-400">PUBLICIDAD</h1>
  <div class="w-[70%] mx-auto pb-4">
    <img class=" rounded-2xl mt-4" src="https://hamburguesasdelrodeo.com/cdn/shop/products/hamburguesa_doble_carne_1024x1024.png?v=1594184497" alt="">
  <img class=" rounded-2xl mt-4" src="https://exitocol.vtexassets.com/arquivos/ids/19937505/Detergente-Liquido-Ariel-Concentrado-Doble-Poder-x-12-Litros-1446696_c.jpg?v=638326504031200000" alt="">
  </div>
 
  </div>
</div>
</template>


