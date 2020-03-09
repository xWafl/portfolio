<template>
    <div class="accordion">
        <div class="accordionSelectors">
            <AccordionElement
                v-for="element in accordionData"
                :id="'accordion-'+element.name"
                :key="element.name"
                :title="element.name"
                :style= "[accordionData.indexOf(element) + 1 === currentAccordion ? {'backgroundColor': '#ccc'} : 'background-color: #fff']"
                @click.native="updateCurrent(accordionData.indexOf(element) + 1)"
            >
                {{element}}
            </AccordionElement>
        </div>
        <transition name="slide-fade" mode="out-in">
            <div
                class="accordionData"
                :key="accordionDataEntry.data"
                :style="[currentAccordion === 0 ? {'background-color': '#eee'} : {'background-color': '#ccc'}]"
            >
<!--                {{pictures[currentAccordion]}}-->
                <div class="accordionDataIcons">
                    <font-awesome-icon
                        v-for="icon in pictures[currentAccordion]"
                        :key="icon.name"
                        :style="{color: icon.color}"
                        :icon="JSON.parse(icon.icon)"
                        class="skillIcon"
                    ></font-awesome-icon>
                    <img
                        v-if="currentAccordion === 2"
                        style="width: 50px; height: 50px"
                        src="https://www.vectorlogo.zone/logos/electronjs/electronjs-icon.svg"
                    />
                    <img
                        v-if="currentAccordion === 2"
                        style="width: 50px; height: 50px"
                        src="https://www.svgrepo.com/show/7344/sql-file-format-symbol.svg"
                    />
                    <img
                        v-if="currentAccordion === 3"
                        src="https://www.vectorlogo.zone/logos/typescriptlang/typescriptlang-icon.svg"
                    />
                </div>
                <div class="accordionDataMessages">
                    {{ accordionDataEntry.data }}
                </div>
            </div>
        </transition>
    </div>
</template>

<script>
    import Vue from 'vue'
    import { library } from '@fortawesome/fontawesome-svg-core'
    import { fas } from '@fortawesome/free-solid-svg-icons'
    import { fab } from '@fortawesome/free-brands-svg-icons'
    import { FontAwesomeIcon } from '@fortawesome/vue-fontawesome'

    library.add(fas);
    library.add(fab);

    Vue.component('font-awesome-icon', FontAwesomeIcon);

    import AccordionElement from "./AccordionElement.vue";
    export default {
        name: "Accordion",
        components: {
            AccordionElement,
        },
        props: {
            accordionData: Array,
            pictures: Array,
        },
        computed: {
            accordionDataEntry: function () {
                // const strippedData = Array.from(this.accordionData, x => x.data);
                // strippedData.unshift("I've got a wide skillset with varying degrees of proficiency. I'm always looking to add more skills, and I try to learn something new everyday.");
                // return strippedData;
                if (this.currentAccordion > 0) {
                    return this.accordionData[this.currentAccordion - 1];
                } else {
                    return {data: "I've got a wide skill set with varying degrees of proficiency. I'm always looking to add more skills, and I try to learn something new every day."}
                }
            }
        },
        data () {
            return {
                currentAccordion: 0,
            }
        },
        methods: {
            updateCurrent (value) {
                if (this.currentAccordion !== value) {
                    this.currentAccordion = value;
                } else {
                    this.currentAccordion = 0;
                }
            }
        }
    }
</script>

<style scoped>
    .accordion {
        border: solid black;
        border-width: 2px 0 2px 0;
        padding: 1px 0 0 0;
        display: flex;
    }
    .accordionSelectors {
        width: 30%;
        /*height: 300px;*/
        display: flex;
        flex-direction: column;
    }
    .accordionData {
        width: 60%;
        height: 220px;
        /*overflow: hidden;*/
        max-height: 220px;
        overflow: auto;
        padding: 10px 5% 10px 5%;
        display: inline-block;
        border-left: 2px solid #bbb;
        font-size: 18px;
    }
    @media only screen and (max-width: 800px) {
        .accordionData {
            max-height: 400px;
        }
    }
    .slide-fade-enter-active {
        transition: all .5s ease;
    }
    .slide-fade-leave-active {
        transition: all .5s ease-in;
    }
    .slide-fade-enter, .slide-fade-leave-to
        /* .slide-fade-leave-active for <2.1.8 */ {
        width: 0%;
        opacity: 0;
        background-color: #fff;
        color: #fff;
    }
    .slide-fade-enter-to, .slide-fade-leave {
        width: 60%;
        opacity: 1;
    }
    .slide-fade-leave-to {
        background-color: #fff;
    }
    .skillIcon {
        font-size: 60px;
        margin: 0px 10px 10px 10px;
    }
</style>