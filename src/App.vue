<script setup>

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
  <div class="col">
    <div class="card">
      <div class="card-body">
        <h5 class="card-title">HP</h5>
        <p class="card-text">$1000</p>
        <p class="card-text">10шт</p>
        <p class="card-text">25.11.2024</p>
        <button type="button" class="btn btn-danger">Удалить</button>
      </div>
    </div>
  </div>
</div>
<h4 class="text-end">Общая сумма товаров: 1000$</h4>
</div>
</template>


