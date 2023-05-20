<script setup>
import { ref, computed } from 'vue'

/*Array de objetos JSON con propiedades (name, lastname)*/
const users = [
  {
    name: 'Jhon',
    lastname: 'Doe',
    age: '30'
  },
  {
    name: 'Jane',
    lastname: 'Doe'
  }
]

const msg = 'sss'
const num = ref(0)

num.value = 2

/*Forma 1*/
// const mostrar1 = () => {
//   alert('Me llaman')
// }

/*Forma 2*/
// const mostrar2 = function() {
//   alert('Me llaman')
// }

/*Forma 3*/
// function mostrar3(){
//   alert('Me llaman')
// }

/*Funcion computada*/
const computado = computed(function () {
  //return num.value > 0 ? num.value * 2 : 0
  if(num.value > 0){
    return num.value *2
  }else{
    return 0
  }
})



</script>

<template>

  Hola {{ msg }} <br>
  valor {{ num }} <br>
  <!-- {{ mostrar3() }} <br> -->
  Valor computado {{ computado }}

  <!-- Ciclos -->
  <!-- Key: identificar cada elemento con el valor de index en cada iteracion-->
  <div v-for="(user, index) in users" :key="index">
   Nombre completo: {{ user.name }} {{ user.lastname }} <br>
   <span v-if="user.age">
    Edad: {{ user.age }}
   </span>
   
  </div>

</template>

<style scoped>

</style>
