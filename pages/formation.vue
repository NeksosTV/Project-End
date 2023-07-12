
<script>
export default {
  data() {
    return {
      realisations: [
        {
          id: 1,
          title: 'PowerUp',
          description: 'Un projet de développement web utilisant les dernières technologies.',
          image: '../public/images/powerup.JPG'
        },
        {
          id: 2,
          title: 'Projet 2',
          description: 'Description du projet 2.',
          image: '/path/to/projet2.jpg'
        },
        {
          id: 3,
          title: 'Projet 3',
          description: 'Description du projet 3.',
          image: '/path/to/projet3.jpg'
        }
      ],
      competences: [
        { id: 1, name: 'Nuxt' },
        { id: 2, name: 'Javascript' },
        { id: 3, name: 'PocketBase' }
      ]
    };
  }
};
</script> 


<template>
 <!-- Projects Section -->
 <section id="projects">
    <div class="projects container">
      <div class="projects-header">
        <h1 class="section-title text-center"> Projects <span>Formation</span></h1>
      </div>
      <div class="all-projects">
        <div class="project-item">
          <div class="project-info">
            <h1>PowerUp</h1>
            <p>Site destiné aux fans de mangas qui regroupe plusieurs personnages et tous les épisodes, avec la possibilité d'ajouter d'autres personnages et épisodes.<a class="LienProjets" target="_blank" href="https://chainsaw-maan.netlify.app/">lien</a></p>
          </div>
          <div class="project-img">
            <img src="../public/images/powerup.JPG" alt="img">
          </div>
        </div>
        <div class="project-item">                                                                                                                            
          <div class="project-info">
            <h1>Présence</h1>
            <p>plateforme de gestion des présences ! Avec notre système convivial et efficace, prendre les présences n'a jamais été aussi simple. <a class="LienProjets" target="_blank" href="https://presence-cedeg.netlify.app/">lien</a></p>
          </div>
          <div class="project-img">
            <img src="../public/images/Présence.PNG" alt="img">
          </div>
        </div>
      </div>
    </div>
  </section> 
  <div class="formation">

    <h2 class="section-title">Compétences acquises</h2>
    <ul class="list">
      <li v-for="competence in competences" :key="competence.id" class="list-item">
        {{ competence.name }}
      </li>
    </ul>
  </div>
</template>

<style>
.formation {
  max-width: 800px;
  margin: 0 auto;
}

.section-title {
  font-size: 24px;
  margin-bottom: 10px;
}

.list {
  list-style-type: disc;
  padding-left: 20px;
}

.list-item {
  margin-bottom: 5px;
}

.realisation-container {
  display: flex;
  align-items: center;
  margin-bottom: 20px;
}

.realisation-image {
  width: 100px;
  height: 100px;
  margin-right: 10px;
}

.realisation-image img {
  width: 100%;
  height: 100%;
  object-fit: cover;
}

.realisation-details {
  flex: 1;
}

.realisation-title {
  font-size: 18px;
  margin-bottom: 5px;
}

.realisation-description {
  font-size: 14px;
}

/* Projects section */
#projects .projects {
	flex-direction: column;
	max-width: 1200px;
	margin: 0 auto;
	padding: 100px 0;
}
#projects .projects-header h1 {
	margin-bottom: 50px;
}
#projects .all-projects {
	display: flex;
	align-items: center;
	justify-content: center;
	flex-direction: column;
}
#projects .project-item {
	display: flex;
	align-items: center;
	justify-content: center;
	flex-direction: column;
	width: 80%;
	margin: 20px auto;
	overflow: hidden;
	border-radius: 10px;
}
#projects .project-info {
	padding: 30px;
	flex-basis: 50%;
	height: 100%;
	display: flex;
	align-items: flex-start;
	justify-content: center;
	flex-direction: column;
	background-image: linear-gradient(60deg, #29323c 0%, #485563 100%);
	color: white;
}
#projects .project-info h1 {
	font-size: 4rem;
	font-weight: 500;
}
#projects .project-info h2 {
	font-size: 1.8rem;
	font-weight: 500;
	margin-top: 10px;
}
#projects .project-info p {
	color: white;
}
#projects .project-img {
	flex-basis: 50%;
	height: 300px;
	overflow: hidden;
	position: relative;
}
#projects .project-img:after {
	content: '';
	position: absolute;
	left: 0;
	top: 0;
	height: 100%;
	width: 100%;
	background-image: linear-gradient(60deg, #29323c 0%, #485563 100%);
	opacity: 0.7;
}
#projects .project-img img {
	transition: 0.3s ease transform;
}
#projects .project-item:hover .project-img img {
	transform: scale(1.1);
}

.LienProjets{
	text-decoration: none;
	color: rgb(187, 0, 0);
	font-size: 1.5em;
}
/* Fin Projects section */
</style>
