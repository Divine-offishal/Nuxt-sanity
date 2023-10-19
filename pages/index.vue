<template>
  <div class="h-screen w-screen">
    <h1 class="text-6xl font-bold text-center my-10 text-green-700">Welcome to a random fashion store</h1>
    <div class="grid grid-cols-4 justify-items-center gap-y-5">
      <Card v-for="(product, i) in data" :key="i" :title="product.name" :price="product.price" :desc="product.desc" :image="product.image.asset._ref"/>
    </div>
  </div>
</template>

<script setup>

  const query = `*[_type == 'product']{name, price, desc, image}`
  const { data } = useSanityQuery(query)


</script>