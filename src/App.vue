<script setup>
const name = "Vue dinamico";
const styleColor = "color: blue";
const activo = false;
const gay = true;
const arrayFrutas = [
  {
    name: "Manzana",
    price: "$1.00",
    description: "Una manzana",
  },
  {
    name: "Pera",
    price: "$2.00",
    description: "Una pera",
  },
  {
    name: "Naranja",
    price: "$3.00",
    description: "Una naranja",
  },
];

const objetoFruta = {
  name: "Manzana",
  price: "$1.00",
  description: "Una manzana",
};

const arrayFrutas2 = [
  {
    name: "Manzana",
    price: "$1.00",
    description: "Una manzana",
    stock: 0,
  },
  {
    name: "Pera",
    price: "$2.00",
    description: "Una pera",
    stock: 10,
  },
  {
    name: "Naranja",
    price: "$3.00",
    description: "Una naranja",
    stock: 20,
  },
];
//metodos
const handleClick = () => {
  console.log("me diste click");
};
const handleClick2 = (mensaje) => {
  console.log(mensaje);
};
</script>

<template>
  <h1>Hola {{ name.toUpperCase() }}</h1>
  <h2 :style="styleColor">Soy azul gracias a v-bind</h2>
  <h2>
    {{ activo ? "Estoy activo" : "Me fui a la verga" }}
  </h2>
  <p v-if="gay">Soy Gay</p>
  <p v-if="!gay">No soy Gay</p>
  <p>{{ arrayFrutas }}</p>
  <p>{{ arrayFrutas[1] }}</p>
  <h1>Recorrer Array</h1>
  <h2>Lista de frutas</h2>
  <ul>
    <li v-for="(fruta, index) in arrayFrutas" :key="fruta.name">
      {{ index + 1 }} - Nombre: {{ fruta.name }} / Precio: {{ fruta.price }} /
      Descripción: {{ fruta.description }}
    </li>
  </ul>

  <h1>Recorrer Objetos</h1>
  <ul>
    <li v-for="(value, propiedad, index) in objetoFruta" :key="value">
      {{ index + 1 }}-- {{ propiedad }} : {{ value }}
    </li>
  </ul>
  <h1>for y for if</h1>
  <ul>
    <template v-for="item in arrayFrutas2" :key="name">
      <li v-if="item.stock > 0">
        {{ item.name }} - {{ item.price }}
      </li></template
    >
  </ul>
  <button @click="handleClick">Activame</button>
  <button @click="handleClick2('hola perro')">Activame 2</button>
</template>

<style>
h1 {
  color: red;
}
</style>
