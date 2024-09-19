<template>
    <div id="app">
      <h1>Login Form</h1>
      <form @submit.prevent="handleLogin">
        <div>
          <label for="username">Username:</label>
          <input v-model="username" type="text" id="username" required />
        </div>
        <div>
          <label for="password">Password:</label>
          <input v-model="password" type="password" id="password" required />
        </div>
        <button type="submit">Login</button>
      </form>
      <p v-if="message">{{ message }}</p>
    </div>
  </template>
  
  <script>
  export default {
    data() {
      return {
        username: '',
        password: '',
        message: ''
      };
    },
    methods: {
      handleLogin() {
        // For demonstration purposes, we're just checking if fields are not empty.
        // In a real application, you would handle authentication here.
        if (this.username && this.password) {
          this.message = `Welcome, ${this.username}!`;
        } else {
          this.message = 'Please enter both username and password.';
        }
      }
    }
  };
  </script>
  
  <style>
  #app {
    max-width: 400px;
    margin: 0 auto;
    padding: 1em;
    text-align: center;
  }
  
  form div {
    margin-bottom: 1em;
  }
  
  label {
    margin-right: 1em;
  }
  
  input {
    padding: 0.5em;
    border: 1px solid #ccc;
    border-radius: 4px;
  }
  
  button {
    padding: 0.7em;
    border: none;
    border-radius: 4px;
    background-color: #28a745;
    color: white;
    cursor: pointer;
  }
  
  button:hover {
    background-color: #218838;
  }
  </style>
  