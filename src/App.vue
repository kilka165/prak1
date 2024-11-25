<script setup>
import { ref } from "vue";
const products = ref([
{
  id: Date.now(),
  name: "HP",
  data: "25.11.2024",
  count: 15,
  price: 100000,
},
{
  id: Date.now(),
  name: "asus",
  data: "25.11.2024",
  count: 152,
  price: 150000,
},
{
  id: Date.now(),
  name: "lenovo",
  data: "25.11.2024",
  count: 5,
  price: 100003,
},
{
  id: Date.now(),
  name: "tesla",
  data: "25.11.2024",
  count: 11,
  price: 102000,
},
]);
</script>

<template>

<div class="contair">
 <div class="rol">
  <div class="mb-3">
  <label for="name" class="form-label">Продукт</label>
  <input type="text" class="form-control" id="name">
 </div>
 <div class="mb-3">
  <label for="data" class="form-label">Дата</label>
  <input type="data" class="form-control" id="data">
 </div>
 <div class="mb-3">
  <label for="count" class="form-label">Количество</label>
  <input type="number" class="form-control" id="count">
 </div>
 <div class="mb-3">
  <label for="count" class="form-label">Цена за единицу товара</label>
  <input type="number" class="form-control" id="count">
 </div>
 <button type="button" class="btn btn-primary">Добавить</button>
 </div>
 <div class="row row-cols-1 row-cols-md-3 g-4">
  <div class="col" v-for="products in products">
    <div class="card">
      <div class="card-body">
        <h5 class="card-title">{{ products.name }}</h5>
        <p class="card-text">{{ products.price }}</p>
        <p class="card-text">{{ products.count }}</p>
        <p class="card-text">{{ products.date }}</p>
        <button type="button" class="btn btn-danger">Удалить</button>
      </div>
    </div>
  </div>
</div>
<h4 class="text-end">Общая сумма товаров: 1000$</h4>
</div>
</template>


