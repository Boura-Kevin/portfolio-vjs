<template>
    <div class="card">

      <h3>Projet CV</h3>
      <p>Date de création : 24 octobre 2023</p>
      <modale :revele="revele" :toggleModale="toggleModale"></modale>
      <div class="btn-modal" v-on:click="toggleModale">Voir</div>
    </div>
</template>
  
  
<script>
  import Modale from "./Modale.vue";
  import Footer from './Footer.vue';
  
  export default {
    name: "Contenu",
    data() {
      return {
        revele: false
      };
    },
    components: {
      modale: Modale
    },
    methods: {
      toggleModale: function() {
        this.revele = !this.revele;
      }
    }
  };
</script>
  
  
<style>
.card {
    display: block;
    margin-top: 5%;
    background-color: aliceblue;
    color: black;
    border-radius: 5%;
    padding: 5%;
    margin: auto;

}

.btn-modal{
    background-color: #00cc00; /* Couleur de fond du bouton */
    color: #ffffff; /* Couleur du texte */
    border: none; /* Supprime la bordure du bouton */
    padding: 10px 20px; /* Espacement intérieur du bouton */
    border-radius: 5px; /* Coins arrondis */
    cursor: pointer; /* Curseur de la souris en forme de main */
  }

.btn-modal:hover{
    background-color: green;
}

</style>