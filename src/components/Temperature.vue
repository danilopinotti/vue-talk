<template>
    <span>
        <span class="display-1" :class="{'font-weight-bold': fontWeightBold}">
            {{value}}º
        </span>
    </span>
</template>

<script>
    export default {
        name: "Temperature",

        props: {
            value: Number,

            fontWeightBold: {
                required: false,
                type: Boolean,
                default: false,
            },
        }
    }
</script>

<style scoped>

</style>