<template>
    <div class="acceuil">
        <h1>Boura Kévin</h1>
        <p>Passionné par la création web, je suis un développeur junior en quête d'opportunités pour mettre en œuvre mes compétences fraîchement acquises et contribuer à la réalisation de projets innovants et captivants.</p>
        <footervue></footervue>
    </div>
</template>

<script>
import Footer from './Footer.vue';


export default {
    name:"Home",
    components: {
        footervue:Footer,
    }

}
</script>

<style>


</style>