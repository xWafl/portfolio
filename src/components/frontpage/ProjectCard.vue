<template>
    <div class="projectCard" :style="{ backgroundImage: 'url(' + backgroundUrl + ')' }">
        <div class="projectDetails" @click="redirectUrl(clickUrl, 'main')">
            <h2 class="projectHeader">{{ hoverHeader }}</h2>
            <p class="projectDesc">{{ hoverText }}</p>
            <div class="projectClick" v-if="usingMobile" @click="redirectUrl(clickUrl, 'smol')">
                Link
            </div>
        </div>
    </div>
</template>

<script lang="ts">
import Vue from 'vue';
import { isMobile } from 'mobile-device-detect';

export default Vue.extend({
    name: "ProjectCard",
    props: {
        backgroundUrl: String,
        hoverHeader: String,
        hoverText: String,
        clickUrl: String,
    },
    data: () => ({
        screenWidth: Number, 
        usingMobile: isMobile,
    }),
    methods: {
        redirectUrl(url, loc) {
            if (loc === "main") {
                if (this.usingMobile === false) {
                    window.location.href = url;
                }
            }
            if (loc === "smol") {
                window.location.href = url;
            }
        },
        getWidth () {
            this.screenWidth = screen.width;
            return this.screenWidth;
        }
    }
})
</script>

<style scoped>
    .projectCard {
        width: 300px;
        height: calc(300px * 1.5);
        margin: 20px;
        font-family:'Courier New', Courier, monospace;
        box-shadow: 0px 0px 20px #999;
        position: relative;
        background-position: center;
        user-select: none;
        flex-shrink: 0;
    }
    @media only screen and (max-width: 340px) {
        .projectCard {
            margin: 20px 10px 20px 10px;
        }
    }
    @media only screen and (min-width: 600px) {
        .projectCard {
            cursor: pointer;
        }
    }
    .projectDetails {
        opacity: 0;
        height: 100%;
        width: 100%;
        position: absolute;
        top: 0px;
        left: 0px;
        background-color: azure;
        color: #222;
        font-weight: bold;
    }
    .projectDetails:hover {
        opacity: 0.8;
        box-shadow: 0px 0px 10px #222;
        transition: 0.6s ease;
    }
    .projectHeader {
        padding-top: 5%;
        color: teal;
        font-weight: bold;
    }
    .projectDesc {
        width: 90%;
        text-align: justify;
        margin: 5%;
    }
    .projectClick {
        width: 70%;
        position: absolute;
        bottom: 15%;
        left: 15%;
        height: 45px;
        line-height: 45px;
        background-color: rgb(220, 235, 235);
        cursor: pointer;
    }
</style>