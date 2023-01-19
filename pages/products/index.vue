<template>
  <div>
    <div class="grid grid-cols-4 gap-5">
      <div v-for="p in products" :key="p.id">
      <ProductCard :product="p"/>
      </div>
    </div>
  </div>
</template>

<script setup>
useHead({
  title: 'Chillings Dojo | Chilled Merch',
  meta: [
    {name: 'description', content: "chilled boy merch"}
  ],
});
definePageMeta({
  layout: 'products-custom',
});
const { data: products } = await useFetch('https://fakestoreapi.com/products');
</script>
