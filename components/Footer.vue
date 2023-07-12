<template>
    <footer class="footer bg-slate-300">
      <div class="footer-logo">
        <img src="../public/images/avion.png" alt="Logo" />
        <h1 class="footer-title">Voyage Ventures</h1>
      </div>
      <div class="footer-toggle" @click="toggleMenu">
        <span class="footer-toggle-icon" :class="{ open: isMenuOpen }"></span>
      </div>
      <!-- <ul :class="['footer-menu', { 'footer-menu-open': isMenuOpen }]">
        <li><a href="#">Accueil</a></li>
        <li><a href="#">À propos</a></li>
        <li><a href="#">Services</a></li>
        <li><a href="#">Contact</a></li>
      </ul> -->
    </footer>
  </template>
  
  <style scoped>
  .footer {
    display: flex;
    justify-content: space-between;
    align-items: center;
    /* background-color: #f0f0f0; */
    padding: 20px;
  }
  
  .footer-logo {
    display: flex;
    align-items: center;
  }
  
  .footer-logo img {
    height: 40px;
    margin-right: 10px;
  }
  
  .footer-title {
    font-size: 24px;
    font-weight: bold;
  }
  
  .footer-toggle {
    display: none;
    cursor: pointer;
  }
  
  .footer-toggle-icon {
    display: block;
    width: 30px;
    height: 2px;
    background-color: #333;
    margin-bottom: 6px;
    transition: transform 0.3s ease;
  }
  
  .footer-toggle-icon.open {
    transform: rotate(45deg);
  }
  
  .footer-toggle-icon::before,
  .footer-toggle-icon::after {
    content: "";
    display: block;
    width: 30px;
    height: 2px;
    background-color: #333;
    transition: transform 0.3s ease;
  }
  
  .footer-toggle-icon.open::before {
    transform: translateY(8px) rotate(45deg);
  }
  
  .footer-toggle-icon.open::after {
    transform: translateY(-8px) rotate(-45deg);
  }
  
  .footer-menu {
    list-style: none;
    display: flex;
  }
  
  .footer-menu li {
    margin-right: 20px;
  }
  
  .footer-menu a {
    color: #333;
    text-decoration: none;
    font-size: 18px;
  }
  
  @media (max-width: 768px) {
    .footer {
      flex-direction: column;
      align-items: flex-start;
    }
  
    .footer-menu {
      display: none;
      flex-direction: column;
      align-items: flex-start;
      margin-top: 20px;
    }
  
    .footer-menu-open {
      display: flex;
    }
  
    .footer-toggle {
      display: flex;
      align-items: center;
    }
  }
  </style>
  
  <script>
  export default {
    data() {
      return {
        isMenuOpen: false
      };
    },
    methods: {
      toggleMenu() {
        this.isMenuOpen = !this.isMenuOpen;
      }
    }
  };
  </script>
  