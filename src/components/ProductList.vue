<script setup>
import ProductCard from './ProductCard.vue'

defineProps({
  products: {
    type: Array,
    required: true,
  },
})

const emit = defineEmits(['delete-product'])
</script>

<template>
  <div class="product-list">
    <ProductCard
      v-for="product in products"
      :key="product.name"
      :product="product"
      @delete="emit('delete-product', product)"
    />
  </div>
</template>

<style scoped>
.product-list {
  display: grid;
  grid-template-columns: repeat(auto-fill, minmax(300px, 1fr));
  gap: 20px;
}
</style>
