<template>
  <div class="product-card">
    <header>
      <div><b>{{ props.product.name }}</b></div>
    </header>
    <main>
      <div>Цена: {{ props.product.price }} руб.</div>
      <div>Производитель: {{ props.product.brand }}</div>
      <slot></slot>
    </main>
    <footer>
      <button type="button" @click="buy">В корзину</button>
    </footer>
  </div>
</template>

<script setup lang="ts">
interface Product {
  name: string;
  price: number;
  brand: string;
}

const props = defineProps<{
  product: Product;
}>();

function buy() {
  alert(`Поздравляем с покупкой ${props.product.brand}`);
}
</script>

<style scoped>
.product-card {
  display: flex;
  gap: 4px;
  flex-direction: column;
  border: 1px solid #ccc;
  padding: 12px;
  border-radius: 8px;
}
</style>