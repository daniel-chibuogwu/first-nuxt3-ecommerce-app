<template>
  <div>
    <Head>
      <Title>Chillings Dojo | {{ product.title }}</Title>
      <Meta name=""/>
    </Head>
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
if (!product.value) {
  throw createError({statusCode: 404, statusMessage: "Product not found", fatal: true});
}
</script>
