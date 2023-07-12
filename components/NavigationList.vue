<template>
    <nav class="navbar bg-slate-300">
      <div class="navbar-logo">
        <img src="../public/images/avion.png" alt="Logo" />
        <h1 class="navbar-title">Voyage Ventures</h1>
      </div>
      <div class="navbar-toggle" @click="toggleMenu">
        <span class="navbar-toggle-icon" :class="{ open: isMenuOpen }"></span>
      </div>
      <ul :class="['navbar-menu', { 'navbar-menu-open': isMenuOpen }]">
        <li><a class="" href="/">Accueil</a></li>
        <li><a href="/formation">formation</a></li>
        <li><a href="/entreprise">Entreprise</a></li>
        <li><a href="/professionnel">Développement professionnel</a></li>
        <!-- <li><a href="#">Contact</a></li> -->
      </ul>
    </nav>
  </template>
  
  <style scoped>
  .navbar {
    display: flex;
    justify-content: space-between;
    align-items: center;
    /* background-color: #f0f0f0; */
    padding: 20px;
  }
  
  .navbar-logo {
    display: flex;
    align-items: center;
  }
  
  .navbar-logo img {
    height: 40px;
    margin-right: 10px;
  }
  
  .navbar-title {
    font-size: 24px;
    font-weight: bold;
  }
  
  .navbar-toggle {
    display: none;
    cursor: pointer;
  }
  
  .navbar-toggle-icon {
    display: block;
    width: 30px;
    height: 2px;
    background-color: #333;
    margin-bottom: 6px;
    transition: transform 0.3s ease;
  }
  
  .navbar-toggle-icon.open {
    transform: rotate(45deg);
  }
  
  .navbar-toggle-icon::before,
  .navbar-toggle-icon::after {
    content: "";
    display: block;
    width: 30px;
    height: 2px;
    background-color: #333;
    transition: transform 0.3s ease;
  }
  
  .navbar-toggle-icon.open::before {
    transform: translateY(8px) rotate(45deg);
  }
  
  .navbar-toggle-icon.open::after {
    transform: translateY(-8px) rotate(-45deg);
  }
  
  .navbar-menu {
    list-style: none;
    display: flex;
  }
  
  .navbar-menu li {
    margin-right: 20px;
  }
  
  .navbar-menu a {
    /* color: #333; */
    text-decoration: none;
    font-size: 18px;
  }
  
  @media (max-width: 768px) {
    .navbar {
      flex-direction: column;
      align-items: flex-start;
    }
  
    .navbar-menu {
      display: none;
      flex-direction: column;
      align-items: flex-start;
      margin-top: 20px;
    }
  
    .navbar-menu-open {
      display: flex;
    }
  
    .navbar-toggle {
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
  