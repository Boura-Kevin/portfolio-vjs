<template>
    <div>
      <h2>Formulaire de Contact</h2>
      <form @submit.prevent="submitForm">
        <label for="name">Nom/Prénom</label>
        <input type="text" id="name" v-model="contact.name" required />
  
        <label for="subject">Objet</label>
        <input type="text" id="subject" v-model="contact.subject" required />
  
        <label for="message">Message</label>
        <textarea id="message" v-model="contact.message" required></textarea>
  
        <button type="submit">Envoyer</button>
      </form>
      <footervue></footervue>
    </div>
</template>
  
<script>

import Footer from './Footer.vue';

export default {
  data() {
    return {
      contact: {
        name: '',
        subject: '',
        message: '',
        components: {
            footervue:Footer,
        },
      },
    };
  },
  methods: {
    async submitForm() {
      
      const formData = new FormData();
      formData.append('name', this.contact.name);
      formData.append('subject', this.contact.subject);
      formData.append('message', this.contact.message);

      try {
        const response = await fetch('/api/send-email', {
            action: "mailto:boura.kevin2002@gmail.com",
            method: 'POST',
            body: formData,
        });

        if (response.ok) {
          
          alert('E-mail envoyé avec succès.');
        } else {
          
          alert('Une erreur s\'est produite lors de l\'envoi de l\'e-mail.');
        }
      } catch (error) {
        
        console.error(error);
        alert('Une erreur s\'est produite.');
      }
    },
  },
};
</script>
<style>
/* Styles pour le formulaire de contact */
form {
  width: 300px;
  margin: 0 auto;
  background: #f5f5f5;
  padding: 5%;
  border-radius: 5px;
  box-shadow: 0px 0px 10px rgba(0, 0, 0, 0.2);
}

h2{
    text-align: center;
    margin-bottom: 5%;
    margin-top: 5%;
}
label {
    position: relative;
    font-weight: bold;
    display: block;
    margin-bottom: 5px;
}

input[type="text"],
input[type="text"]:focus,
input[type="text"]:active,
input[type="text"]:hover,
textarea,
textarea:focus,
textarea:active,
textarea:hover {
    width: 100%;
    padding: 10px;
    margin-bottom: 10px;
    border: 1px solid #ccc;
    border-radius: 5px;
}

textarea {
    position: relative;
    height: 100px;
}

button {
    background: #0077cc;
    color: #fff;
    border: none;
    padding: 10px 20px;
    border-radius: 5px;
    cursor: pointer;
    font-weight: bold;
}

button:hover {
  background: #0055aa;
}
</style>
