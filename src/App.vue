<template>
    <div id="app">
        <TitleCard :name="name"></TitleCard>
        <AboutMe :name="name"></AboutMe>
        <SocialLinks></SocialLinks>
        <br>
        <Skills></Skills>
        <br><br>
        <h2 style="font-size: 40px;">Portfolio</h2>
        <div id="projectDivs">
            <ProjectCard :backgroundUrl="petrisIcon" hoverHeader="Petris" hoverText="A web version of Tetris with a lot of modifications. It's a research project for the P vs NP problem." clickUrl="http://petris.herokuapp.com"></ProjectCard>
            <ProjectCard :backgroundUrl="waterdropIcon" hoverHeader="This site!" hoverText="This site is actually a finished front end project, and it's the project that I'm the most proud of my design for." clickUrl="/"></ProjectCard>
            <ProjectCard backgroundUrl="https://www.jing.fm/clipimg/detail/221-2218831_clip-art-stock-vector-trading-chart-stock-market.png" hoverHeader="Skymarket" hoverText="An auction house analyzer for the game Hypixel Skyblock. Granted, I didn't make the backend, but I did a lot of the front-end and data analysis." clickUrl="http://xwafl.github.io/skymarket"></ProjectCard>
        </div>
        <br><br>
    </div>
</template>

<script>
import TitleCard from './components/frontpage/TitleCard.vue';
import AboutMe from './components/frontpage/AboutMe.vue';
import Skills from './components/frontpage/Skills.vue';
import ProjectCard from './components/frontpage/ProjectCard.vue';
import SocialLinks from './components/SocialLinks.vue';
// import Divider from './components/utility/Divider.vue';

/* eslint-disable no-new */

export default {
    name: 'App',
    components: {
        TitleCard,
        AboutMe,
        SocialLinks,
        Skills,
        ProjectCard
        // Divider
    },
    data: () => ({
        name: "ImperialWater"
    }),
    computed: {
        waterdropIcon () {
            return require('./assets/waterdrop.png')
        },
        petrisIcon () {
            return require('./assets/512x512.png')
        }
    }
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
    width: calc(100%);
}
#projectDivs {
    width: 100%;
    display: flex;
    justify-content: center;
    flex-shrink: 0;
    flex-wrap: wrap;
}
</style>