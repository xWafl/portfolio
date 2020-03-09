<template>
    <div id="app">
        <TitleCard :name="name"></TitleCard>
        <AboutMe :name="name"></AboutMe>
        <SocialLinks></SocialLinks>
        <br>
<!--        <Skills></Skills>-->
        <h2 class="skillsHeader">My skills</h2>
        <h3 class="skillsSubheader">I try to learn something new every day.</h3>
        <Accordion
            :accordionData="[
                {name: 'Advanced', data: 'My focus is on web development. I\'ve picked Vue as my main framework, and I\'d say that I\'m decent at it. I also know HTML, CSS, and JS. I\'ve got a good knowledge of JS, but it\'s such a huge language that there\'s always more to learn. I can work with the OOP principles of JS, as well as HTTP requests and APIs.'},
                {name: 'Proficient', data: 'I\'m proficient in other languages besides my main. I can work well with NodeJS, and I understand many of the concepts in it such as callbacks, promises, and async/await. I can also work with SQL databases, but my main focus is on Postgres. I also really enjoy drinking water, and I can drink a whole glass in 6 seconds.'},
                {name: 'Beginner', data: 'There are a few languages that I\'m not so good at, but can still use. Before I used Vue, I used Angular, and my knowledge of that is rusty at best. I also have worked with C, but I haven\'t really used it for any projects. I\'m decent at Git, and I can do things like pull requests, rebases, etc. I also use TypeScript a lot, I\'m not great at it by any means, and the types system is still magical to me, but I use it in almost all my projects.'}
            ]"
            :pictures='[
                    [

                    ],
                    [
                        {name: "Vue", color:"#41B883", icon:"[\"fab\", \"vuejs\"]"},
                        {name: "HTML", color:"#E44D26", icon:"[\"fab\", \"html5\"]"},
                        {name: "CSS", color:"#264de4", icon:"[\"fab\", \"css3-alt\"]"},
                        {name: "JS", color:"#F0DB4F", icon:"[\"fab\", \"js\"]"}
                    ],
                    [
                        {name: "NodeJS", color:"#68A063", icon:"[\"fab\", \"node-js\"]"},
                        {name: "Water", color:"#61dbfb", icon:"[\"fas\", \"glass-whiskey\"]"}
                    ],
                    [
                        {name: "Angular", color:"#B52E31", icon:"[\"fab\", \"angular\"]"},
                        {name: "C", color:"#3949AB", icon:"[\"fab\", \"cuttlefish\"]"},
                        {name: "Git", color:"#F1502F", icon:"[\"fab\", \"git-alt\"]"},
                    ]
                ]'
        ></Accordion>
        <br><br>
        <h2 style="font-size: 40px;">Portfolio</h2>
        <div id="projectDivs">
            <ProjectCard :backgroundUrl="petrisIcon" hoverHeader="Petris" hoverText="A web version of Tetris with a lot of changes. It's a research project for the P vs NP problem." clickUrl="http://petris.herokuapp.com"></ProjectCard>
            <ProjectCard :backgroundUrl="waterdropIcon" hoverHeader="This site!" hoverText="This site is actually a finished front end project, and it's the project that I'm the most proud of my design for." clickUrl="/"></ProjectCard>
            <ProjectCard backgroundUrl="https://www.jing.fm/clipimg/detail/221-2218831_clip-art-stock-vector-trading-chart-stock-market.png" hoverHeader="Skymarket" hoverText="An auction house analyzer for the game Hypixel Skyblock. Granted, I didn't make the backend, but I did a lot of the front-end and data analysis." clickUrl="http://xwafl.github.io/skymarket"></ProjectCard>
        </div>
        <br>
        <br><br>
    </div>
</template>

<script>
import TitleCard from './components/frontpage/TitleCard.vue';
import AboutMe from './components/frontpage/AboutMe.vue';
// import Skills from './components/frontpage/Skills.vue';
import ProjectCard from './components/frontpage/ProjectCard.vue';
import SocialLinks from './components/SocialLinks.vue';
import Accordion from './components/frontpage/Accordion.vue';
// import Divider from './components/utility/Divider.vue';

/* eslint-disable */

export default {
    name: 'App',
    components: {
        TitleCard,
        AboutMe,
        SocialLinks,
        // Skills,
        ProjectCard,
        Accordion,
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
    font-family: Calibri, Avenir, Helvetica, Arial, sans-serif;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    text-align: center;
    color: #2c3e50;
    position: absolute;
    top: 0;
    left: 0;
    width: calc(100%);
}
#projectDivs {
    width: 100%;
    display: flex;
    justify-content: center;
    flex-shrink: 0;
    flex-wrap: wrap;
}
.skillsHeader {
    text-align: center;
    font-size: 40px;
    font-weight: bold;
    font-family: "Century Gothic";
}
.skillsSubheader {
    font-size: 30px;
    text-align: center;
    font-family: "Century Gothic";
}
</style>