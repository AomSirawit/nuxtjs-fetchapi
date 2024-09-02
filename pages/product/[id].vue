<template>
  <div class="max-w-lg mx-auto p-4 bg-white shadow-lg rounded-lg my-10">
    <img :src="product.thumbnail" alt="Product Image" class="w-full rounded-lg mb-4" />
    <div class="text-gray-700">
      <p class="text-xl font-bold mb-2">{{ product.title }}</p>
      <p class="text-lg mb-2">Category: <span class="text-gray-500">{{ product.category }}</span></p>
      <p class="text-lg mb-2">Brand: <span class="text-gray-500">{{ product.brand }}</span></p>
      <p class="text-lg mb-4">Description: <span class="text-gray-600">{{ product.description }}</span></p>
      <p class="text-xl font-semibold">Price: <span class="text-green-600">{{ product.price }} $</span></p>
      <div class="flex justify-center items-center">
      <NuxtLink
            to="#"
            class="inline-flex items-center justify-center px-5 py-3 text-base font-medium text-center bg-blue-700 text-white rounded-lg"
          >
            Buy Now !
          </NuxtLink>
        </div>
    </div>
  </div>
</template>

<script setup>
  const { id } = useRoute().params;
  const { data: product } = await useFetch("https://dummyjson.com/products/" + id);
</script>

<style scoped></style>
