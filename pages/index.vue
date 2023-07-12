<template>
    <!-- <div>
      <section class="home-section">
        <div class="home-banner">
          <div class="home-banner-image"></div>
        </div>
        <div class="home-content">
          <h1 class="home-title">Bienvenue sur notre site de Voyages</h1>
          <p class="home-description">Lorem ipsum dolor sit amet, consectetur adipiscing elit.</p>
        </div>
      </section>
    </div> -->

    <div class="container mt-5">
    <div class="card">
      <div class="card-header">
        <h1 class="text-center">{{ nom }} {{ prenom }}</h1>
      </div>
      <div class="card-body">
        <p>{{ formation }}</p>
      </div>
    </div>
  </div>
    
  <div class="profile">
    <div class="profile-header">
      <img :src="profilePicture" alt="Profile Picture" class="profile-picture">
      <h1 class="profile-name">{{ fullName }}</h1>
      <h3 class="profile-title">{{ headline }}</h3>
    </div>


    <div class="profile-experience">
      <ul>
        <li v-for="experience in experiences" :key="experience.id" class="experience-item">
          <h3 class="text-center">{{ experience.title }}</h3>
          <p>{{ experience.company }}</p>
          <p>{{ experience.duration }}</p>
          <p>{{ experience.description }}</p>
        </li>
      </ul>
    </div>

    <div class="profile-summary">
      <p>{{ summary }}</p>
    </div>

    <h3 class="profile-title">{{ sessionforma }}</h3>
    <div class="profile-skills">
      <h2>Compétences :</h2>
      <ul>
        <li v-for="skill in skills" :key="skill.id" class="skill-item">{{ skill.name }}</li>
      </ul>
    </div>
  </div>

  
  </template>

<script>
export default {
  data() {
    return {
      // nom: 'Lamboray',
      // prenom: 'Florian',
      // formation: 'Ce que vous avez fait pendant votre formation',
      fullName: "Florian Lamboray",
      profilePicture: "../public/images/cedeg.png",
      sessionforma: "4 mois de formation a la cedeg",
      headline: "Développeur Web",
      summary: "Passionné par le développement web et les technologies frontend et Back-end, je suis à la recherche de nouvelles opportunités pour mettre en pratique mes compétences et contribuer à des projets innovants.",
      experiences: [
        {
          id: 1,
          title: "Présentation",
          // company: "XYZ Company",
          // duration: "2019 - Présent",
          description: "Responsable du développement et de la maintenance de sites web utilisant les dernières technologies frontend et backend. Participation active à la conception, à l'optimisation des performances et à la résolution de problèmes."
        },
        // Ajoutez ici d'autres expériences professionnelles
      ],
      skills: [
        { id: 1, name: "HTML" },
        { id: 2, name: "CSS" },
        { id: 3, name: "JavaScript" },
        { id: 4, name: "Nuxt" },
        { id: 5, name: "Angular" },
        { id: 6, name: "php" },
        { id: 7, name: "sql server" }
        // Ajoutez ici d'autres compétences
      ]
    };
  },
};
</script>
  
  <style scoped>

.card {
  width: 400px;
  margin: 0 auto;
}

  .home-section {
    background-color: #f0f0f0;
    padding: 40px 20px;
    text-align: center;
    margin-top: 0;
  }
  
  .home-banner {
    display: flex;
    justify-content: center;
    align-items: center;

  }
  
  .home-banner-image {
    width: 100%;
    height: 300px;
    background-image: url("../public/images/placez-vol-dans-ciel-du-coucher-du-soleil.jpg");
    background-size: cover;
    background-position: center;

  }
  
  .home-title {
    font-size: 24px;
    font-weight: bold;
    margin-bottom: 10px;
  }
  
  .home-description {
    font-size: 18px;
    color: #333;
  }
  
  @media (min-width: 768px) {
    .home-section {
      padding: 80px 40px;
    }
  }






  .profile {
  max-width: 800px;
  margin: 0 auto;
  padding: 20px;
  animation: fade-in 1s ease-out;
}

@keyframes fade-in {
  0% {
    opacity: 0;
    transform: translateY(20px);
  }
  100% {
    opacity: 1;
    transform: translateY(0);
  }
}

.profile-header {
  display: flex;
  flex-direction: column;
  align-items: center;
  margin-bottom: 20px;
}

.profile-picture {
  width:650px;
  height: 250px;
  object-fit: cover;
  border-radius: 25%;
}

.profile-name {
  font-size: 24px;
  margin-top: 10px;
}

.profile-title {
  font-size: 18px;
  margin-top: 5px;
  color: #888;
}

.profile-summary {
  margin-bottom: 20px;
  animation: slide-up 1s ease-out;
}

@keyframes slide-up {
 0% {
    opacity: 0;
    transform: translateY(20px);
  }
  100% {
    opacity: 1;
    transform: translateY(0);
  }
}

.profile-experience {
  margin-bottom: 20px;
  animation: slide-up 1s ease-out;
}

.experience-item {
  margin-bottom: 10px;
  padding-bottom: 10px;
  border-bottom: 1px solid #ddd;
  animation: fade-in 1s ease-out;
}

.profile-skills {
  animation: slide-up 1s ease-out;
}

.skill-item {
  display: inline-block;
  margin-right: 10px;
  margin-bottom: 5px;
  padding: 5px 10px;
  border-radius: 20px;
  background-color: #f5f5f5;
  color: #888;
  animation: fade-in 1s ease-out;
}
  </style>
  