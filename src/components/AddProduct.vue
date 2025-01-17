<script setup>
import { ref } from 'vue'

const emit = defineEmits(['add-product'])

const name = ref('')
const imageSrc = ref('')
const description = ref('')
const price = ref('')

const handleSubmit = () => {
  if (!name.value || !description.value || !price.value) return

  emit('add-product', {
    name: name.value,
    imageSrc: imageSrc.value || '/placeholder-image.png', // Default image if none provided
    description: description.value,
    price: Number(price.value),
  })

  // Reset form
  name.value = ''
  imageSrc.value = ''
  description.value = ''
  price.value = ''
}
</script>

<template>
  <div class="add-product">
    <h2>Add New Product</h2>
    <form @submit.prevent="handleSubmit" class="add-product-form">
      <div class="form-group">
        <label for="name">Name:</label>
        <input id="name" v-model="name" type="text" required />
      </div>

      <div class="form-group">
        <label for="image">Image URL: (optional)</label>
        <input id="image" v-model="imageSrc" type="url" />
      </div>

      <div class="form-group">
        <label for="price">Price ($):</label>
        <input id="price" v-model="price" type="number" min="0" step="0.01" required />
      </div>

      <div class="form-group">
        <label for="description">Description:</label>
        <textarea id="description" v-model="description" required></textarea>
      </div>

      <button type="submit">Add Product</button>
    </form>
  </div>
</template>

<style scoped>
.add-product {
  background: linear-gradient(to bottom, #376ec8 16%, #69b7e5 95%);
  padding: 20px;
  border-radius: 8px;
  margin: 0 auto 20px;
  max-width: 600px;
}

.add-product-form {
  display: flex;
  flex-direction: column;
  gap: 15px;
}

.form-group {
  margin-bottom: 15px;
}

label {
  display: block;
  margin-bottom: 5px;
}

input,
textarea {
  width: 100%;
  padding: 8px;
  border: 1px solid #ddd;
  border-radius: 4px;
}

button {
  background: #376ec8;
  color: white;
  border: none;
  padding: 10px 20px;
  border-radius: 4px;
  cursor: pointer;
}

button:hover {
  background: #2856a8;
}
</style>
