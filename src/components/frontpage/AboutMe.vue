<template>
    <div class="aboutme">
        <div class="lefthalf">
            <h2 class="aboutmetitle">{{ name }}</h2>
            <img id="profileimg" src="../../assets/waterdrop.png" />
        </div>
        <Divider dividerType="regular"></Divider>
        <div class="righthalf">
            <h2 class="whoami">Who am I?</h2>
            <p class="mydesc">I'm a developer with a focus on front-end. My specialty is in JavaScript although I do know some other languages such as TypeScript and C. I'm always looking to learn something new!</p>
        </div>
    </div>
</template>

<script lang="ts">
import Vue from 'vue'
import Divider from "../utility/Divider.vue"

export default Vue.extend({
    name: "AboutMe",
    props: {
        name: String
    },
    components: {
        Divider
    }
})
</script>

<style scoped>
    .aboutme {
        width: 100%;
        color: #111;
        background-color: white;
    }
    .aboutmetitle {
        float: left;
        margin: 10% 0% 7% 0%;
        /* margin-top: 5%; */
        width: 100%;
        font-size: 36px;
        text-align: center;
    }
    #profileimg {
        /* width: 50%; */
        height: 300px;
        border: 3px solid #eee;
        border-radius: 30px;
    }
    @media only screen and (min-width: 901px) {
        .aboutme {
            display: flex;
            height: 500px;
        }
        .lefthalf {
            width: calc(50% - 5px);
        }
        .righthalf {
            width: calc(50% - 5px);
        }
        .whoami {
            font-size: 36px;
            text-align: center;
            width: 100%;
            margin: 10% 0% 7% 0%;
            float: right;
        }
        .mydesc {
            font-size: 24px;
            text-align: justify;
            width: 80%;
            margin: 15% 0% 0% 10%;
        }
    }
    @media only screen and (max-width: 900px) {
        .lefthalf {
            width: 100%;
        }
        .righthalf {
            width: 100%;
        }
        .whoami {
            font-size: 36px;
            text-align: center;
            width: 100%;
        }
        .mydesc {
            font-size: 20px;
            text-align: justify;
            width: 80%;
            margin: 15% 0% 0% 10%;
        }
    }
</style>