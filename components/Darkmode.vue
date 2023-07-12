<template>
    <div :class="['container', { 'dark-mode': isDarkMode }]">
      <h1 class="text-center mt-5">Mon Component</h1>
  
      <!-- Contenu du composant -->
  
      <button @click="toggleDarkMode" class="toggle-button">
        {{ isDarkMode ? 'Mode Clair' : 'Mode Sombre' }}
      </button>
    </div>
  </template>
  
  <script>
  export default {
    data() {
      return {
        isDarkMode: false,
      };
    },
    methods: {
      toggleDarkMode() {
        this.isDarkMode = !this.isDarkMode;
        // Stocker la préférence du mode sombre dans localStorage ou Vuex pour la persister entre les pages ou rechargements
      },
    },
  };
  </script>
  
  <style scoped>

  
  .dark-mode {
    background-color: #666666;
    color: #fff;
  }
  
  .toggle-button {
    position: fixed;
    bottom: 20px;
    right: 20px;
    padding: 10px 20px;
    border: none;
    border-radius: 4px;
    background-color: #fff;
    color: #222;
    cursor: pointer;
  }
  </style>
  