<template>
  <nav class="bg-gray-800 p-4">
    <div class="container mx-auto flex justify-between items-center">
      <!-- Left Navigation Links -->
      <div class="hidden md:flex space-x-6">
        <NuxtLink to="/" class="text-white hover:text-gray-300">Home</NuxtLink>
        <NuxtLink to="/about" class="text-white hover:text-gray-300">About</NuxtLink>
      </div>

      <!-- Centered Logo -->
      <div class="flex justify-center">
        <img src="@/assets/logo.png" alt="Logo" class="h-10 w-10">
      </div>

      <!-- Right Navigation Links -->
      <div class="hidden md:flex space-x-6">
        <NuxtLink to="/services" class="text-white hover:text-gray-300">Services</NuxtLink>
        <NuxtLink to="/contact" class="text-white hover:text-gray-300">Contact</NuxtLink>
      </div>

      <!-- Mobile Menu Button -->
      <button @click="toggleMenu" class="text-white md:hidden">
        <svg xmlns="http://www.w3.org/2000/svg" class="h-6 w-6" fill="none" viewBox="0 0 24 24" stroke="currentColor">
          <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M4 6h16M4 12h16m-7 6h7" />
        </svg>
      </button>
    </div>
    
    <!-- Mobile Navigation Links -->
    <div v-if="isOpen" class="md:hidden flex flex-col space-y-2 p-4">
      <NuxtLink to="/" class="text-white hover:text-gray-300">Home</NuxtLink>
      <NuxtLink to="/about" class="text-white hover:text-gray-300">About</NuxtLink>
      <NuxtLink to="/services" class="text-white hover:text-gray-300">Services</NuxtLink>
      <NuxtLink to="/contact" class="text-white hover:text-gray-300">Contact</NuxtLink>
    </div>
  </nav>
</template>

<script>
export default {
  data() {
    return {
      isOpen: false,
    };
  },
  methods: {
    toggleMenu() {
      this.isOpen = !this.isOpen;
    },
  },
};
</script>

<style scoped>
/* Custom styles if needed */
</style>
