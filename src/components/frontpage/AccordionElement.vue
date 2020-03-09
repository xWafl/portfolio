<template>
    <div class="accordionElement">
        <h3>{{ title }}</h3>
    </div>
</template>

<script>
    export default {
        name: "AccordionElement",
        props: {
            title: String
        }
    }
</script>

<style scoped>
    .accordionElement {
        width: 100%;
        height: 80px;
        line-height: 40px;
        text-align: center;
        transition: background-color 1s;
    }
    .accordionElement:hover {
        background-color: #ddd;
    }
</style>