<template>
    <div class="professional-page">
      <h1 class="page-title">CV et Lettre de motivation</h1>
      <div class="documents">
        <embed :src="cvPath" width="800px" height="1000px" />
        <embed :src="lettreMotivationPath" width="800px" height="1000px" />
        <!-- <embed src="https://chainsaw-maan.netlify.app/" width="800px" height="1000px" /> -->
        <a :href="cvPath" target="_blank" class="document-link">CV</a>
        <a :href="lettreMotivationPath" target="_blank" class="document-link">Lettre de motivation</a>
      </div>
      <h2 class="section-title">Tâches réalisées pendant la formation</h2>
      <ul class="task-list">
        <li v-for="tache in taches" :key="tache.id" class="task-item">{{ tache.nom }}</li>
      </ul>

      <h2 class="section-title">Plan d'action</h2>
      <textarea v-model="planAction" rows="5" class="action-plan"></textarea>
    </div>
  </template>
  
  <script>
  export default {
    data() {
      return {
        cvPath: "../public/perso/Lamboray Florian CV.pdf",
        lettreMotivationPath: "../public/perso/FlorianLamboray-LettreMotivation.pdf",
        taches: [
          { id: 1, nom: "Création d'un site pour un café fictive" },
          { id: 2, nom: "Création d'un site pour un shop fictive" },
          { id: 3, nom: "Création d'un site rick et morty" },
          { id: 4, nom: "Création d'un site pour les fans de mangas PowerUp" }
        ],
        planAction: "Je vais rechercher un travail qui va me permette de bouger et de ne pas rester sur place. L'informatique reste une passion pour moi, mais je n'ai plus l'envie d'en faire mon métier."
      };
    }
  };
  </script>
  
  <style>
  .professional-page {
    max-width: 800px;
    margin: 0 auto;
    padding: 20px;
  }
  
  .page-title {
    font-size: 24px;
    margin-bottom: 20px;
  }
  
  .documents {
    margin-bottom: 20px;
  }
  
  .document-link {
    display: block;
    margin-bottom: 10px;
    color: #007bff;
    text-decoration: none;
  }
  
  .document-link:hover {
    text-decoration: underline;
  }
  
  .section-title {
    font-size: 20px;
    margin-bottom: 10px;
  }
  
  .task-list {
    list-style-type: disc;
    padding-left: 20px;
  }
  
  .task-item {
    margin-bottom: 5px;
  }
  
  .action-plan {
    width: 100%;
    margin-top: 10px;
    padding: 5px;
    font-size: 16px;
  }
  </style>
  