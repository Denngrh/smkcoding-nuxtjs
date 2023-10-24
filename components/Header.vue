<template>
  <header class="bg-blue-500 p-4">
    <div class="container mx-auto flex justify-between items-center">
      <nuxt-link to="/" class="text-white text-xl font-bold">SMK Coding</nuxt-link>
      <div class="hidden md:flex space-x-4">
        <nuxt-link to="/" class="text-white text-xl font-bold" :class="{'text-yellow-500': isActive('/')}" exact-active-class="text-yellow-500">Home</nuxt-link>
        <nuxt-link to="/product" class="text-white text-xl font-bold"
          exact-active-class="text-yellow-500">Product</nuxt-link>
        <nuxt-link to="/cart" class="text-white text-xl font-bold" exact-active-class="text-yellow-500">Cart</nuxt-link>
      </div>
      <div class="md:hidden flex space-x-4">
        <div class="relative group">
          <button @click="mobileMenuOpen = !mobileMenuOpen" class="text-white text-xl">
            ☰
          </button>
          <div v-if="mobileMenuOpen"
            class="absolute top-0 right-0 mt-10 w-48 bg-blue-500 border border-white p-4 space-y-4 text-white">
            <nuxt-link to="/" class="text-white text-xl font-bold" :class="{'text-yellow-500': isActive('/')}" exact-active-class="text-yellow-500">Home</nuxt-link>
            <nuxt-link to="/product" class="block" exact-active-class="text-yellow-500">Product</nuxt-link>
            <nuxt-link to="/cart" class="block" exact-active-class="text-yellow-500">Cart</nuxt-link>
          </div>
        </div>
      </div>
    </div>
  </header>
</template>

  
<script>
export default {
  data() {
    return {
      mobileMenuOpen: false
    };
  },
  methods: {
    isActive(route) {
      return this.$route.path === route;
    }
  }
};

</script>
  