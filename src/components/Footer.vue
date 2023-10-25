<template>
    <footer>
      <div class="social-icons">
        <a href="https://github.com/Boura-Kevin" target="_blank">
          <img src="https://cdn-icons-png.flaticon.com/512/25/25231.png" alt="GitHub" />
        </a>
        <a href="https://www.linkedin.com/in/votreprofil" target="_blank">
          <img src="https://cdn-icons-png.flaticon.com/512/174/174857.png" alt="LinkedIn" />
        </a>
        <!-- Ajoutez d'autres icônes et liens vers vos réseaux sociaux ici -->
      </div>
      <p>Dernière mise à jour : {{ getLastUpdateDate() }}</p>
    </footer>
</template>
  
<script>
  export default {
    name: "Footervue",
    methods: {
      getLastUpdateDate() {
        return '24 octobre 2023';
      },
    },
  };
</script>

<style>
/* Styles pour le footer */
footer {
    position: static;
    background: #333; /* Couleur de fond du footer */
    color: #fff; /* Couleur du texte */
    text-align: center;
    padding: 20px 0; /* Espacement intérieur */
    bottom: 0; /* Ancrer le footer au bas de la page */
    width: 100%; /* Étirer le footer sur toute la largeur de l'écran */
}

.social-icons img{
    width: 5%;
    margin-bottom: 10px;
}

.social-icons a {
  margin: 0 10px;
  text-decoration: none;
  color: #fff;
  font-size: 24px;
}
</style>

  