<script setup>
import { ref } from 'vue'
let contador = ref(0)
function addValue() {
  contador.value++
}
function decreaseValue() {
  if (contador.value >= 1) {
    contador.value--
  }
}
</script>
<template>
  <div class="wrapper">
    <div class="profile">
      <div class="notification" v-if="contador>=1">{{ contador }}</div>
    </div>
    <div class="button-wrapper">
      <div class="button" @click="addValue">+</div>
      <div class="button" @click="decreaseValue">-</div>
    </div>
    <div v-if="contador==0">Buuuu! Nadie te escribe👻</div>
    <div v-else>Revisa tu inbox 🤭</div>
  </div>
</template>

<style scoped>
.wrapper {
  background-color: #3f7c85;
  width: 40%;
  border-radius: 15px;
  margin: 0 auto;
  padding-top: 32px;
  overflow: hidden;
  text-align: center;
}
.profile {
  background-color: pink;
  width: 250px;
  height: 250px;
  border-radius: 50%;
  margin: 0 auto;
  position: relative;
  background: url('https://metrovisualoptica.co/cdn/shop/collections/custom_resized_8b9f4d49-4fa4-4a04-8998-282df2188cbc.jpg?v=1647015001&width=750');
  background-size: cover;
}

.notification {
  position: absolute;
  background-color: #ff5f5d;
  color: white;
  font-weight: 700;
  border-radius: 50%;
  width: 60px;
  height: 60px;
  display: flex;
  align-items: center;
  justify-content: center;
  top: 0;
  right: 0;
}
.button-wrapper {
  text-align: center;
  /* background-color: aqua; */
  padding: 15px 0;
}
.button {
  background-color: #00ccbf;
  border-radius: 4px;
  padding: 10px 0;
  font-weight: bold;
  color: white;
  display: inline-block;
  width: 40px;
  cursor: pointer;
}
.button:first-child {
  margin-right: 10px;
}
.button:last-child {
  margin-left: 10px;
}
</style>
