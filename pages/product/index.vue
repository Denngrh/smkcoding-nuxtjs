<script lang="ts" setup>
import { products } from '~/composables/constants/products';
const allProducts = ref(products);
</script>
<template>
    <section>
        <div class="container">
            <div class="py-10">
                <div class="grid grid-cols-1 sm:grid-cols-2 md:grid-cols-3 lg:grid-cols-4 gap-6">
                    <template v-for="(item, index) in allProducts" :key="index">
                        <CardsCardProduct :product="item" class="w-full" />
                    </template>
                </div>
            </div>
        </div>
    </section>
</template>
  