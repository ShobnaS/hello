<template>
    <form @submit.prevent="handleSubmit" class="hello">
      <label for="name">Name : </label>
      <input type="text" id="name" required v-model="name" /><br><br>
  
      <label for="email">Email : </label>
      <input type="email" id="email" required v-model="email" /><br><br>
  
      <label for="passwords">Password : </label>
      <input type="password" id="passwords" required v-model="password" /><br><br>
  
      <label for="tel">Phone : </label>
      <input type="tel" id="tel" required v-model="phone" /><br><br>
  
      <button type="submit">Submit</button>
    </form>
  </template>
  
  <script>
  export default {
    name: "MyForm",
    data() {
      return {
        name: '',
        email: '',
        password: '',
        phone: ''
      };
    },
    methods: {
      handleSubmit() {
        const formData = {
          name: this.name,
          email: this.email,
          password: this.password,
          phone: this.phone
        };
  
    
        localStorage.setItem('userFormData', JSON.stringify(formData));
  
       
        console.log("Form data saved:", formData);
  
      
        this.name = '';
        this.email = '';
        this.password = '';
        this.phone = '';
      }
    }
  };
  </script>
  <style scoped>
  .hello {
    text-align: left;
    width: 300px;
    padding: 20px;
    border: 1px solid #ccc;
    border-radius: 10px;
    background-color: #fff;
    box-shadow: 0 2px 8px rgba(0, 0, 0, 0.1);
    margin: auto;
  }
  
  
  html, body {
    height: 100%;
    margin: 0;
    display: flex;
    justify-content: center; 
    align-items: center;     
    background-color: #f0f2f5; 
  }
  </style>
  