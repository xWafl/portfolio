<template>
    <div class="divider" :class="{ regularDivider: dividerType === 'regular', horizontalDivider: dividerType === 'horizontal'}">

    </div>
</template>

<script>
export default {
    name: "Divider",
    props: {
        dividerType: String,
    }
}
</script>

<style>
    .horizontalDivider {
        width: 2px;
        border: 4px solid #eee;
        border-radius: 5px;
        background-color: #eee;
        height: 90%;
        margin-top: 2.5%;
    }
    @media only screen and (min-width: 901px) {
        .regularDivider {
            width: 2px;
            border: 4px solid #eee;
            border-radius: 5px;
            background-color: #eee;
            height: 90%;
            margin-top: 2.5%;
        }
    }
    @media only screen and (max-width: 900px) {
        .regularDivider {
            height: 2px;
            border: 4px solid #eee;
            border-radius: 5px;
            width: 90%;
            margin: 5%;
            background-color: #eee;
        }
    }
</style>