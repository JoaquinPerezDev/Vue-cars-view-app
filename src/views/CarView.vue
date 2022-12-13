<script setup>
  import {useRoute, useRouter, RouterView} from "vue-router"
  import cars from "../data/cars.json"

  const route = useRoute()
  const router = useRouter()
  const carId = parseInt(route.params.id)
  const car = cars.find(car => car.id === carId)
  
</script>

<template>
  <div>
    <h1>{{car.name}}</h1>
    <p>Year: {{car.year}}</p>
    <p>Price: ${{car.price}}</p>
    <button @click="router.push(`/cars/${carId}/contact`)">Click for contact</button>
    <RouterView  />
  </div>
</template>