<template>
  <div>
    <section class="bg-white dark:bg-gray-900">
      <div
        class="grid max-w-screen-xl px-4 py-8 mx-auto lg:gap-8 xl:gap-0 lg:py-16 lg:grid-cols-12"
      >
        <div class="mr-auto place-self-center lg:col-span-7">
          <h1
            class="max-w-2xl mb-4 text-4xl font-extrabold tracking-tight leading-none md:text-5xl xl:text-6xl dark:text-white"
          >
            Welcome To ITFeature Shop
          </h1>
          <p
            class="max-w-2xl mb-6 font-light text-gray-500 lg:mb-8 md:text-lg lg:text-xl dark:text-gray-400"
          >
            Lorem ipsum dolor sit amet consectetur adipisicing elit. Recusandae
            perspiciatis laudantium quo perferendis id facere pariatur omnis
            maiores, ratione accusamus sed! Recusandae quod quam autem qui
            voluptatem quisquam facere facilis!
          </p>
          <NuxtLink
            to="/product"
            class="inline-flex items-center justify-center px-5 py-3 text-base font-medium text-center text-gray-900 border border-gray-300 rounded-lg hover:bg-gray-100 focus:ring-4 focus:ring-gray-100 dark:text-white dark:border-gray-700 dark:hover:bg-gray-700 dark:focus:ring-gray-800"
          >
            Buy Now !
          </NuxtLink>
        </div>
        <div class="hidden lg:mt-0 lg:col-span-5 lg:flex">
          <img
            src="https://flowbite.s3.amazonaws.com/blocks/marketing-ui/hero/phone-mockup.png"
            alt="mockup"
          />
        </div>
      </div>
    </section>
    <div class="m-10">
        <h1 class="text-2xl font-semibold">Popular Products</h1>
        <div class="grid grid-cols-1 gap-4 my-10 md:grid-cols-2 lg:grid-cols-4">
             <div v-for="item in product.products" :key="item.id">
            <div
              class="max-w-sm bg-white border border-gray-200 rounded-lg shadow-lg"
            >
              <NuxtLink :to="`/product/${item.id}`">
                <img :src="item.thumbnail" alt="" />
              </NuxtLink>
              <div class="p-5">
                <a href="#">
                  <h5
                    class="mb-2 text-2xl font-bold tracking-tight text-gray-900"
                  >
                   {{ item.title }}
                  </h5>
                </a>
                <p class="mb-3 font-normal text-gray-700 dark:text-gray-400">
                  {{ item.description }}
                </p>
                <p class="mb-3 font-normal text-green-600">
                  {{ item.price }} $
                </p>
                <NuxtLink :to="`/product/${item.id}`"
                  
                  class="inline-flex items-center px-3 py-2 text-sm font-medium text-center text-white bg-blue-700 rounded-lg hover:bg-blue-800 focus:ring-4 focus:outline-none focus:ring-blue-300 dark:bg-blue-600 dark:hover:bg-blue-700 dark:focus:ring-blue-800"
                >
                  Read more
                  <svg
                    class="rtl:rotate-180 w-3.5 h-3.5 ms-2"
                    aria-hidden="true"
                    xmlns="http://www.w3.org/2000/svg"
                    fill="none"
                    viewBox="0 0 14 10"
                  >
                    <path
                      stroke="currentColor"
                      stroke-linecap="round"
                      stroke-linejoin="round"
                      stroke-width="2"
                      d="M1 5h12m0 0L9 1m4 4L9 9"
                    />
                  </svg>
                </NuxtLink>
              </div>
            </div>
          </div>
        </div>
        <div class="flex justify-center items-center">
          <NuxtLink
            to="/product"
            class="text-white bg-gray-800 hover:bg-gray-900 focus:outline-none focus:ring-4 focus:ring-gray-300 font-medium rounded-lg text-sm px-5 py-2.5 me-2 mb-2 dark:bg-gray-800 dark:hover:bg-gray-700 dark:focus:ring-gray-700 dark:border-gray-700">
            More
          </NuxtLink>
        </div>
      </div>

  </div>
</template>

<script setup>
  const { data: product } = await useFetch(
    "https://dummyjson.com/products?limit=4"
  );
  console.log(product)
  </script>

<style scoped></style>
