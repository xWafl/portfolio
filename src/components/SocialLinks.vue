<template>
    <div class="socialLinks">
        <h3 class="socialLinksHeader">Contact me!</h3>
        <a href="https://github.com/xWafl"><font-awesome-icon class="socialMediaIcon github" :icon="['fab', 'github']" /></a>
        <a href="https://twitter.com/imperial_water"><font-awesome-icon class="socialMediaIcon twitter" :icon="['fab', 'twitter']" /></a>
        <a href="https://www.twitch.tv/imperialwaffle521/"><font-awesome-icon class="socialMediaIcon twitch" :icon="['fab', 'twitch']" /></a>
        <a href="https://www.reddit.com/user/thedankiestmanalive"><font-awesome-icon class="socialMediaIcon reddit" :icon="['fab', 'reddit']" /></a>
        <a href="https://discordapp.com/users/371244109383335937"><font-awesome-icon class="socialMediaIcon discord" :icon="['fab', 'discord']" /></a>
    </div>
</template>

<script lang="ts">
import Vue from 'vue'
import { library } from '@fortawesome/fontawesome-svg-core'
// import { faUserSecret } from '@fortawesome/free-solid-svg-icons'
import { fab } from '@fortawesome/free-brands-svg-icons'
import { FontAwesomeIcon } from '@fortawesome/vue-fontawesome'

// library.add(faUserSecret)
library.add(fab);

Vue.component('font-awesome-icon', FontAwesomeIcon);

/* eslint-disable no-new */

export default Vue.extend({
    name: "SocialLinks"
})
</script>

<style>
    .socialLinks {
        width: 100%;
        /* height: 160px; */
        /* background-color: rgb(102, 168, 255); */
        background-color: #ccc;
        color: #ddd;
        font-size: 60px;
        font-family: Verdana, Arial,sans-serif;
    }
    .socialMediaIcon {
        padding: 10px;
        height: 60px;
        vertical-align: middle;
        background-color: #88aaff;
        margin: 5px;
        border: 5px #88aaff solid;
        border-radius: 5px;
        transition: background-color 0.5s ease, border-color 0.5s ease;
    }
    .socialLinksHeader {
        font-size: 40px;
        margin: 10px;
        padding: 10px;
        color: #444
    }
    .github:hover {
        background-color: black;
        border-color: black;
    }
    .twitter:hover {
        background-color: #00aced;
        border-color: #00aced;
    }
    .twitch:hover {
        background-color: #6441a5;
        border-color: #6441a5;
    }
    .reddit:hover {
        background-color: #ff5700;
        border-color: #ff5700;
    }
    .discord:hover {
        background-color: #7289da;
        border-color: #7289da;
    }
    @media only screen and (max-width: 900px) {
        .github {
            background-color: black;
            border-color: black;
        }
        .twitter {
            background-color: #00aced;
            border-color: #00aced;
        }
        .twitch {
            background-color: #6441a5;
            border-color: #6441a5;
        }
        .reddit {
            background-color: #ff5700;
            border-color: #ff5700;
        }
        .discord {
            background-color: #7289da;
            border-color: #7289da;
        }
    }
    a:visited {
        text-decoration: none;
        color: white;
    }
    a {
        text-decoration: none;
        color: white;
    }
    a:active {
        text-decoration: none;
        color: white;
    }
    a:hover {
        text-decoration: none;
        color: white;
    }
</style>
