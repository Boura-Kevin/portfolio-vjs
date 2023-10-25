<template>
  <div id="app">
    <div class="navigation">
      <a href="#/">Home</a> |
      <a href="#/formulaire">Formulaire</a> |
      <a href="#/projets">Projets</a> |
      <a href="#/non-existent-path">Page 404</a>
      
      <component :is="currentView" />
    </div>
    
  </div>
  
    
</template>

<script>
import Contenu from "./components/Contenu.vue";
import Form from "./components/Form.vue";
import NotFound from './components/NotFound.vue';
import Home from './components/Home.vue';



const routes = {
  '/': Home,
  '/formulaire': Form,
  '/projets': Contenu,
}

export default {
  data() {
    return {
      currentPath: window.location.hash,
    }
  },
  computed: {
    currentView() {
      return routes[this.currentPath.slice(1) || '/'] || NotFound
    }
  },
  mounted() {
    window.addEventListener('hashchange', () => {
		  this.currentPath = window.location.hash
		})
  }
}
</script>

<style>



</style>
