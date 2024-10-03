<template>
    <div class="new-component">
      <h1>Create New Item</h1>
      <form @submit.prevent="handleSubmit">
        <div class="form-group">
          <label for="title">Title:</label>
          <input v-model="formData.title" type="text" id="title" placeholder="Enter title" />
        </div>
  
        <div class="form-group">
          <label for="description">Description:</label>
          <textarea v-model="formData.description" id="description" placeholder="Enter description"></textarea>
        </div>
  
        <button type="submit" class="submit-btn">Submit</button>
      </form>
  
      <div v-if="submitted">
        <h2>Submission Result</h2>
        <p><strong>Title:</strong> {{ formData.title }}</p>
        <p><strong>Description:</strong> {{ formData.description }}</p>
      </div>
    </div>
  </template>
  
  <script setup>
  import { ref } from 'vue';
  
  const formData = ref({
    title: '',
    description: ''
  });
  const submitted = ref(false);
  
  const handleSubmit = () => {
    submitted.value = true;
    // Here, you could also send formData to an API or process it further
  };
  </script>
  
  <style scoped>
  .new-component {
    max-width: 600px;
    margin: 0 auto;
    padding: 20px;
    border: 1px solid #ccc;
    border-radius: 10px;
    background-color: #f9f9f9;
  }
  
  .form-group {
    margin-bottom: 15px;
  }
  
  .form-group label {
    display: block;
    margin-bottom: 5px;
  }
  
  .form-group input,
  .form-group textarea {
    width: 100%;
    padding: 8px;
    box-sizing: border-box;
  }
  
  .submit-btn {
    padding: 10px 20px;
    background-color: #4CAF50;
    color: white;
    border: none;
    border-radius: 5px;
    cursor: pointer;
  }
  
  .submit-btn:hover {
    background-color: #45a049;
  }
  
  h2 {
    margin-top: 20px;
  }
  </style>
  