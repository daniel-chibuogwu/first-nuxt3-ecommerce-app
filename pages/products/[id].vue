<template>
  <div>
  <ProductDetails :product="product"/>
  </div>
</template>

<script setup>

definePageMeta({
  layout: 'products-custom',
});
const { id }  = useRoute().params;
const uri = `https://fakestoreapi.com/products/${id}`;
const {data: product } = await useFetch(uri, {key: id});
</script>

<style scoped>

</style>
