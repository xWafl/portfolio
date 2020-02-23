<template>
    <div class="titlecard">
        <div class="title" id="title">
            <!-- <img class="profileImage" src="img/profile.jpg" alt="Image cannot be displayed"> -->
            <div class="fadeIn">
                <h2 class="name">{{ name }}</h2>
                <h4 class= "subtitle">Web Developer</h4>
            </div>
        </div>
        <div class="parallax"></div>
    </div>
</template>

<script lang="ts">
import Vue from 'vue'
export default Vue.extend({
    name: "TitleCard",
    props: {
        name: String
    },
    methods: {
        handleScroll () {
            const titleElement = document.getElementById("title");
            // console.log(window.scrollY + "|" + titleElement.clientHeight);
            titleElement.style.opacity = (1 - window.scrollY / +titleElement.clientHeight * 1.75).toString();
        }
    },
    created () {
        window.addEventListener('scroll', this.handleScroll);
    },
    destroyed () {
        window.removeEventListener('scroll', this.handleScroll);
    }
})
</script>

<style scoped>
    .parallax {
        height: 100vh;
        width: 100%;
        background-image: url('../../assets/water2.jpg');
        background-position: center;
        background-attachment: fixed;
        background-repeat: no-repeat;
        background-size: cover;
    }
    .fadeIn {
        opacity: 1;
    }
    .title {
        position: absolute;
        text-align: center;
        width: 100%;
        top: 10%;
        color: rgb(64, 64, 255);
    }
    @media only screen and (min-width: 901px) {
        .title {
            font-size: 40px;
        }
    }
    @media only screen and (max-width: 900px) {
        .title {
            font-size: 30px;
        }
    }
    .name {
        padding-top: 220px;
    }
    .subtitle {
        margin-top: -20px;
        color: blue;
        font-size: 24px;
    }
</style>