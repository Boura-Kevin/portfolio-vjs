<template>
    <div class="bloc-modale" v-if="revele">
    <div class="overlay" v-on:click="toggleModale"></div>

    <div class="modale">
      <div v-on:click="toggleModale" class="btn-modale">X</div>
      <h2>CV</h2>
      <img src="../assets/image.png" alt="image du site">
      <p>Date de création : 24 octobre 2023</p>
      <p>Technologies utilisées : HTML, CSS, JavaScript</p>
      <a href="https://github.com/Boura-Kevin/CV/tree/main/CV" target="_blank">Repository GitHub</a>
    </div>
  </div>
  </template>
  
  
  <script>
  export default {
    name: "Modale",
    props: ["revele", "toggleModale"]
  };
  </script>
  
  
  <style scoped>
  .bloc-modale {
    
  display: flex;
  justify-content: center;
  align-items: center;
}

.overlay {
  background: rgba(0, 0, 0, 0.5);
  position: fixed;
  top: 0;
  bottom: 0;
  left: 0;
  right: 0;
}

.modale {
  background: #f1f1f1;
  color: #333;
  padding: 5%;
  position: relative;
  margin:10%
}

.modale img {
  width: 100%;
  height: auto;
}

.btn-modale {
  position: absolute;
  top: 10px;
  right: 10px;
  background-color: #ff0000; /* Couleur de fond du bouton */
  color: #ffffff; /* Couleur du texte */
  border: none; /* Supprime la bordure du bouton */
  padding: 5px 15px; /* Espacement intérieur du bouton */
  border-radius: 5px; /* Coins arrondis */
  cursor: pointer; /* Curseur de la souris en forme de main */
}

.btn-modale:hover{
  background-color: #cc0000;

  
}

@media (max-width: 600px) {
  .modale {
    width: 90%;
    padding: 10px;
    font-size: 14px;
  }
}
</style>