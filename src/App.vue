<template>
    <div id="app">
        <TitleCard :name="name"></TitleCard>
        <AboutMe :name="name"></AboutMe>
        <SocialLinks></SocialLinks>
        <br>
        <Skills></Skills>
    </div>
</template>

<script>
import TitleCard from './components/frontpage/TitleCard.vue';
import AboutMe from './components/frontpage/AboutMe.vue';
import Skills from './components/frontpage/Skills.vue';
import SocialLinks from './components/SocialLinks.vue';

export default {
    name: 'App',
    components: {
        TitleCard,
        AboutMe,
        SocialLinks,
        Skills
    },
    data: () => ({
        name: "ImperialWater"
    })
}
</script>

<style>
#app {
    font-family: Avenir, Helvetica, Arial, sans-serif;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    text-align: center;
    color: #2c3e50;
    position: absolute;
    top: 0px;
    left: 0px;
    width: 100%;
}
</style>
