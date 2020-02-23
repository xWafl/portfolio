<template>
    <div class="skills">
        <h2 class="skillsHeader">My skills</h2>
        <h3 class="skillsSubheader">I try to learn something new every day.</h3>
        <div class="skillChart">
            <div class="skillColumns frontendSkills">
                <h3 class="skillMinorHeading">Advanced</h3>
                <font-awesome-icon class="skillIcon" :icon="['fab', 'vuejs']" />
                <br>
                <font-awesome-icon class="skillIcon" :icon="['fab', 'html5']" />
                <br>
                <font-awesome-icon class="skillIcon" :icon="['fab', 'css3-alt']" />
                <br>
                <font-awesome-icon class="skillIcon" :icon="['fab', 'js']" />
                <br>
            </div>
            <div class="skillColumns backendSkills">
                <h3 class="skillMinorHeading">Proficient</h3>
                <font-awesome-icon class="skillIcon" :icon="['fab', 'node-js']" />
                <br>
                //TODO: GET RID OF THE WATER
                <font-awesome-icon class="skillIcon" :icon="['fas', 'glass-whiskey']" />
                <br>
                <img style="width: 50px; height: 50px" src="../../assets/electronicon.svg" />
            </div>
            <div class="skillColumns otherSkills">
                <h3 class="skillMinorHeading">Beginner</h3>
                <font-awesome-icon class="skillIcon" :icon="['fab', 'angular']" />
                <br>
                <font-awesome-icon class="skillIcon" :icon="['fab', 'cuttlefish']" />
                <br>
                <font-awesome-icon class="skillIcon" :icon="['fab', 'git-alt']" />
                <br>
                <img src="../../assets/typescript.svg" />
            </div>
        </div>
    </div>
</template>

<script lang="ts">
import Vue from 'vue'
import { library } from '@fortawesome/fontawesome-svg-core'
import { fas } from '@fortawesome/free-solid-svg-icons'
import { fab } from '@fortawesome/free-brands-svg-icons'
import { FontAwesomeIcon } from '@fortawesome/vue-fontawesome'

library.add(fas)
library.add(fab)

Vue.component('font-awesome-icon', FontAwesomeIcon)

/* eslint-disable no-new */

export default Vue.extend({
    name: "Skills"
})
</script>

<style>
    .skills {
        width: 100%;
    }
    .skillsHeader {
        text-align: center;
        font-size: 40px;
        font-weight: bold;
    }
    .skillsSubheader {
        font-size: 30px;
        text-align: center;
    }
    .skillMinorHeading {
        font-size: 24px;
        font-weight: bold;
    }
    .skillChart {
        display: flex;
    }
    .skillIcon {
        font-size: 60px;
    }
    .skillColumns {
        flex-basis: 100%;
    }
</style>