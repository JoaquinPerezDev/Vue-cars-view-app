<script setup>
  import {useRoute, RouterView} from "vue-router";
  import cars from "../data/cars.json";

  const route = useRoute()
  const car = cars.find(car => car.id === parseInt(route.params.id))
  
</script>

<template>
  <div>
    <h1>{{car.name}}</h1>
    <p>Year: {{car.year}}</p>
    <p>Price: ${{car.price}}</p>
    <RouterView  />
  </div>
</template>