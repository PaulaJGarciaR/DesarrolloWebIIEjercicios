<script setup>

</script>

<template>
<div class="card">
  <h1>Listas Cosas</h1>
  <p class="subtitle">tarea nueva</p>
  <div>
    <div class="task">TareaUno <span class="button">x</span></div>
    <div class="task">TareaDos <span class="button">x</span></div>
  </div>
  <div>
    <input type="text" placeholder="Escribe tu tarea">
    <p>Presiona para confirmar</p>
  </div>
</div>
</template>

<style scoped>
.button{
  background-color: #002333;
  color: white;
  padding: 0 5px;
  border-radius: 4px;
  justify-content: center;
}

.task:hover{
  background-color: #159A9C ;
  color:white;
}
.task{
  display: flex;
  justify-content: space-between;
  background-color: #DEEFE7;
  border-radius: 4px;
  padding: 2px 8px;
  margin-bottom: 2px;
}
.subtitle{
  padding:0;
  margin:0;
  text-align: center;
  opacity: 0.6;
}
h1{
  text-transform: uppercase;
  text-align: center;
  padding: 0;
  margin: 0;
  font-size: 30px;
}
.card{
  background-color: #B4BEC9;
  max-width: 350px;
  border-radius: 8px;
  padding: 18px 16px;
 margin: 0 auto;
 font-family: 'Oswald', sans-serif;
}
</style>
