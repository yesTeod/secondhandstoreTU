<script setup>
import { ref } from 'vue'

const emit = defineEmits(['add-product'])

const name = ref('')
const imageSrc = ref('')
const description = ref('')

const handleSubmit = () => {
  if (!name.value || !imageSrc.value || !description.value) return

  emit('add-product', {
    name: name.value,
    imageSrc: imageSrc.value,
    description: description.value,
  })

  // Reset form
  name.value = ''
  imageSrc.value = ''
  description.value = ''
}
</script>

<template>
  <div class="add-product">
    <h2>Add New Product</h2>
    <form @submit.prevent="handleSubmit">
      <div class="form-group">
        <label for="name">Name:</label>
        <input id="name" v-model="name" type="text" required />
      </div>

      <div class="form-group">
        <label for="image">Image URL:</label>
        <input id="image" v-model="imageSrc" type="url" required />
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
  background: white;
  padding: 20px;
  border-radius: 8px;
  margin-bottom: 20px;
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
