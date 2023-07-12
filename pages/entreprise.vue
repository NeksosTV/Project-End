<template>
    <div class="container">
      <h1 class="text-center mt-5">Bienvenue chez Voyages et Tourisme</h1>
  
      <p class="text-center mt-3">
        Chez Voyages et Tourisme,  sommes passionnés par les voyages et nous nous engageons à vous offrir les meilleures expériences de voyage possibles. Que vous recherchiez une voiture de location pour explorer votre destination, des excursions inoubliables ou des réservations d'hôtels et de vols pratiques, notre site de voyage est là pour répondre à tous vos besoins.
      </p>
  
      <div class="row mt-5">
        <div class="col-md-4">
          <div class="card mb-4">
            <img src="../public/images/voiture.png" class="card-img-top" alt="Service de location de voiture">
            <div class="card-body">
              <h3 class="card-title">Service de location de voiture</h3>
              <p class="card-text">Explorez votre destination à votre propre rythme en louant une voiture confortable et fiable. Notre service de location de voiture vous offre une large gamme de véhicules adaptés à tous les besoins et budgets.</p>
              <a href="#" class="btn btn-primary">réserver</a>
            </div>
          </div>
        </div>
  
        <div class="col-md-4">
          <div class="card mb-4">
            <img src="../public/images/excursion.png" class="card-img-top" alt="Excursions et visites guidées">
            <div class="card-body">
              <h3 class="card-title">Excursions et visites guidées</h3>
              <p class="card-text">Découvrez les merveilles de chaque destination avec nos excursions et visites guidées passionnantes. Nos guides locaux expérimentés vous feront vivre des expériences authentiques et inoubliables.</p>
              <a href="#" class="btn btn-primary">réserver</a>
            </div>
          </div>
        </div>
  
        <div class="col-md-4">
          <div class="card mb-4">
            <img src="../public/images/hotel.png" class="card-img-top" alt="Réservation d'hôtels et de vols">
            <div class="card-body">
              <h3 class="card-title">Réservation d'hôtels et de vols</h3>
              <p class="card-text">Simplifiez vos voyages en réservant vos hôtels et vols avec notre service pratique de réservation en ligne. Nous vous offrons un large choix d'hébergements et d'options de vol pour que vous puissiez personnaliser votre voyage selon vos préférences.</p>
              <a href="#" class="btn btn-primary">réserver</a>
            </div>
          </div>
        </div>
      </div>
    </div>

    <div class="contact-form">
    <p v-if="errorMessage" class="error-message">{{ errorMessage }}</p>
    <p v-if="successMessage" class="success-message">{{ successMessage }}</p>
    <h1>Formulaire de contact</h1>

    <form @submit.prevent="submitForm">
      <div class="form-group">
        <label for="email">Email :</label>
        <input type="email" id="email" v-model="email" required>
      </div>

      <div class="form-group">
        <label for="message">Message :</label>
        <textarea id="message" v-model="message" required></textarea>
      </div>

      <button type="submit">Envoyer</button>
    </form>


  </div>
  </template>
  
  <script>

import PocketBase from 'pocketbase';
 export default {
  data() {
    return {
      email: '',
      message: '', // Correction de la propriété "massage" en "message"
      errorMessage: '',
      successMessage: ''
    };
  },
  methods: {
    async submitForm() {
      const pb = new PocketBase('http://127.0.0.1:8090');

      const item = {
        email: this.email,
        message: this.message // Correction de la propriété "massage" en "message"
      };

      try {
        const record = await pb.collection('contact').create(item);
        console.log('Données enregistrées avec succès:', record);

        this.successMessage = "Message envoyé !";
        console.log(record);
        // Réinitialiser les champs du formulaire
        this.email = '';
        this.message = '';
      } catch (error) {
        console.error('Erreur lors de l\'enregistrement des données:', error);
        this.errorMessage = "Une erreur s'est produite lors de l'envoi du message.";
      }
    }
  }
};
  </script>
  
  <style>
  .container {
    max-width: 900px;
    margin: 0 auto;
  }
  
  .text-center {
    text-align: center;
  }
  
  .mt-5 {
    margin-top: 2rem;
  }
  
  .row {
    margin-left: -15px;
    margin-right: -15px;
  }
  
  .col-md-6 {
    flex-basis: 50%;
    max-width: 50%;
    padding-left: 15px;
    padding-right: 15px;
  }
  
  .card {
    transition: transform 0.3s;
    margin-bottom: 1.5rem;
  }
  
  .card:hover {
    transform: translateY(-5px);
  }
  
  .card-img-top {
    height: 200px;
    object-fit: cover;
  }
  
  .card-title {
    font-size: 1.5rem;
    font-weight: bold;
    margin-bottom: 0.5rem;
  }
  
  .card-text {
    color: #242323;
    margin-bottom: 1rem;
  }
  
  .btn-primary {
    background-color: #007bff;
    color: #fff;
    border: none;
  }
  
  .btn-primary:hover {
    background-color: #0056b3;
  }
  
  .btn {
    padding: 0.75rem 1.5rem;
    font-size: 1rem;
    border-radius: 3px;
    cursor: pointer;
  }

  /* body {
  background-image: url("../public/images/bg.jpg");
  background-size: cover;
  filter: blur(5px);
} */
.contact-form {
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  height: 100vh;
  background-image: url('../public/images/bg.jpg');
  background-size: cover;
  padding: 20px;
}

h1 {
  color: #000000;
  font-size: 24px;
  margin-bottom: 20px;
}

.form-group {
  margin-bottom: 15px;
}

label {
  display: block;
  color: #000000;
  margin-bottom: 5px;
  font-weight: bold;
}

input,
textarea {
  width: 300px;
  padding: 10px;
  border-radius: 4px;
  border: none;
}

textarea {
  height: 150px;
}

button {
  width: 300px;
  background-color: #4caf50;
  color: rgb(0, 0, 0);
  padding: 10px 20px;
  border: none;
  border-radius: 4px;
  cursor: pointer;
  font-weight: bold;
  transition: background-color 0.3s ease;
}

button:hover {
  background-color: #45a049;
}

.error-message {
  color: red;
  margin-top: 10px;
}

.success-message {
  color: green;
  margin-top: 10px;
}
  </style>
  