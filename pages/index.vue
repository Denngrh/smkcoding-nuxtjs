<script lang="ts" setup>
import { products } from '~/composables/constants/products';
const selectedCategory = ref("");
const allProducts = computed(() => {
    if (selectedCategory.value) {
        return products.filter((item) => item.category === selectedCategory.value);
    }
    return products;
});
</script>

<template>
    <section>
      <div class="container">
        <div class="py-10">
          <div class="mb-6 flex justify-end gap-6">
            <Dropdown class="md:mb-0 lg:mb-6" @selected-category="selectedCategory = $event" />
          </div>
          <div class="grid grid-cols-1 sm:grid-cols-2 md:grid-cols-4 lg:grid-cols-4 xl:grid-cols-4 gap-4">
            <template v-for="(item, index) in allProducts" :key="index">
              <CardsCardProduct :product="item" class="w-full" />
            </template>
          </div>
        </div>
      </div>
    </section>
  </template>  
