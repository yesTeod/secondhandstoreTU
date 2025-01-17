<script setup>
const props = defineProps({
  product: {
    type: Object,
    required: true,
  },
})

const emit = defineEmits(['delete', 'buy'])

const formatPrice = (price) => {
  return `$${price.toFixed(2)}`
}
</script>

<template>
  <div class="product-card">
    <img
      :src="product.imageSrc"
      :alt="product.name"
      @error="$event.target.src = '/placeholder-image.png'"
    />
    <div class="product-info">
      <h3>{{ product.name }}</h3>
      <p class="price">{{ formatPrice(product.price) }}</p>
      <p class="description">{{ product.description }}</p>
      <div class="button-group">
        <button @click="emit('delete')" class="delete-btn">Delete</button>
        <button @click="emit('buy')" class="buy-btn">Buy {{ formatPrice(product.price) }}</button>
      </div>
    </div>
  </div>
</template>

<style scoped>
.product-card {
  background: white;
  border-radius: 8px;
  overflow: hidden;
  box-shadow: 0 2px 4px rgba(0, 0, 0, 0.1);
}

img {
  width: 100%;
  height: 200px;
  object-fit: cover;
}

.product-info {
  padding: 15px;
}

h3 {
  margin: 0 0 10px 0;
}

.price {
  font-size: 1.2em;
  font-weight: bold;
  color: #376ec8;
  margin: 10px 0;
}

.description {
  margin: 0 0 15px 0;
  color: #666;
}

.button-group {
  display: flex;
  gap: 10px;
}

.delete-btn,
.buy-btn {
  flex: 1;
  padding: 8px 16px;
  border: none;
  border-radius: 4px;
  cursor: pointer;
  font-weight: bold;
}

.delete-btn {
  background: #ff4444;
  color: white;
}

.buy-btn {
  background: #4caf50;
  color: white;
}

.delete-btn:hover {
  background: #cc0000;
}

.buy-btn:hover {
  background: #45a049;
}
</style>
