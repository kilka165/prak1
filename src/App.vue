<script setup>
import { ref, computed } from "vue";
const products = ref([
  {
    id: 1,
    name: 'Tesla',
    date: "25.11.2024",
    count: 10,
    price: 4000,
  },
  {
    id: 2,
    name: 'HP',
    date: "25.11.2024",
    count: 18,
    price: 1500,
  },
  {
    id: 3,
    name: 'Acer',
    date: "25.11.2024",
    count: 20,
    price: 2500,
  },
  {
    id: 4,
    name: 'Asus',
    date: "25.11.2024",
    count: 25,
    price: 3500,
  },
]);

const name = ref('');
const date = ref('');
const count = ref(1);
const price = ref(0);

const addProduct = () => {
  if (name.value && date.value && count.value && price.value) {
    products.value.push({
    id: Date.now(),
    name: name.value,
    date: date.value,
    count: count.value,
    price: price.value,
    })
  }
}
const removeProduct = (id) => {
  products.value = products.value.filter((products) => products.id != id)
}
const totalSum = computed (() => {
  return products.value.reduce((sum,product) => sum + (product.price * product.count), 0);
}) 
</script>

<template>
  <div class="container">
    <div class="row">

    <div class="col">
      <h1 class="text-center my-3">Учет товаров</h1>

      <div class="mb-3">
  <label for="name" class="form-label">Название</label>
  <input type="text" v-model="name"  class="form-control" id="name">
  </div>

  <div class="mb-3">
  <label for="date" class="form-label">Дата</label>
  <input type="date" v-model="date" class="form-control" id="date">
  </div>

  <div class="mb-3">
  <label for="count" class="form-label">Количество</label>
  <input type="number" v-model="count" class="form-control" id="count">
  </div>

  <div class="mb-3">
  <label for="price" class="form-label">Цена</label>
  <input type="number" v-model="price" class="form-control" id="price">
  </div>
  <button type="button" class="btn btn-success" @click="addProduct">Добавить</button>

</div>

<div class="row row-cols-1 row-cols-md-3 g-4">
  <div class="col" v-for="products in products">
    <div class="card h-100">
      <div class="card-body">
        <h5 class="card-title">{{ products.name }}</h5>
        <p class="card-text">${{ products.price }}</p>
        <p class="card-text">{{ products.count }}</p>
        <p class="card-text">{{ products.date }}</p>
      </div>
      <div class="card-footer text-end">
        <button class="btn btn-outline-danger" @click="removeProduct(products.id)">Удалить</button>
      </div>
    </div>
  </div>
</div>

</div>
<div class="row my-4">
<div class="col">
<h3 class="text-end">Общая сумма товаров: ${{ totalSum }}</h3>
</div>
</div>
</div>
</template>