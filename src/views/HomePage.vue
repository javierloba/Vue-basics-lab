<template>
  <div class="wrapper">
    <input type="number" v-model="num1" />
    <input type="number" v-model="num2" />
    <p>{{ result }}</p>
    <button @click="suma">Haz click para sumar</button>
    <button @click="resta">Haz click para restar</button>
    <p v-show="counter > 0">El número es {{ counter }}</p>
    <ul>
      <li v-for="dummys in dummyData" :key="dummys.title">
        {{ dummys.title }} - {{ dummys.description }} - {{ dummys.content }}
      </li>
    </ul>
    <button @click="changeColor">Cambia el color</button>
    <div :style="{ color }">Cambio de color</div>
  </div>
</template>

<script setup>
import { ref, computed } from "vue";

const num1 = ref(2);
const num2 = ref(4);
const counter = ref(0);
const myColor = ref("limegreen");
const dummyData = [
  { title: "Title 1", description: "Description 1", content: "Some content 1" },
  { title: "Title 2", description: "Description 2", content: "Some content 2" },
  { title: "Title 3", description: "Description 3", content: "Some content 3" },
];

let result = computed(() => num1.value + num2.value);
let color = computed(() => myColor.value);
let changeColor = () => (myColor.value = "red");
let suma = () => counter.value++;
let resta = () => counter.value--;
</script>

<style>
.wrapper {
  display: flex;
  align-items: center;
  flex-direction: column;
  width: 100vw;
}
div {
  margin-top: 20px;
}
</style>
