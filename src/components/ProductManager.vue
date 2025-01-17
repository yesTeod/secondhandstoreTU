<script setup>
import { ref, computed } from 'vue'
import AddProduct from './AddProduct.vue'
import ProductFilter from './ProductFilter.vue'
import ProductList from './ProductList.vue'

const products = ref([])
const filterText = ref('')

const filteredProducts = computed(() => {
  return products.value.filter((product) =>
    product.name.toLowerCase().includes(filterText.value.toLowerCase()),
  )
})

const handleAddProduct = (newProduct) => {
  products.value.push(newProduct)
}

const handleFilterChange = (text) => {
  filterText.value = text
}

const handleDeleteProduct = (productToDelete) => {
  const index = products.value.findIndex((p) => p.name === productToDelete.name)
  if (index !== -1) {
    products.value.splice(index, 1)
  }
}

const handleBuyProduct = (product) => {
  alert(`Thank you for purchasing ${product.name} for ${product.price.toFixed(2)}!`)
  // Here you could add additional logic for purchase handling
}
</script>

<template>
  <div class="product-manager">
    <AddProduct @add-product="handleAddProduct" />
    <ProductFilter v-model="filterText" />
    <ProductList
      :products="filteredProducts"
      @delete-product="handleDeleteProduct"
      @buy-product="handleBuyProduct"
    />
  </div>
</template>

<style scoped>
.product-manager {
  max-width: 1200px;
  margin: 0 auto;
  padding: 0 20px;
}
</style>
