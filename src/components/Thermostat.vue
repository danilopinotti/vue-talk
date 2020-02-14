<template>
    <span>
        <button class="btn btn-info btn-md" @click="coolDown">
            <i class="fa fa-snowflake"></i>
        </button>
        <button class="btn btn-danger btn-md ml-1" @click="heatUp">
            <i class="fa fa-fire"></i>
        </button>
    </span>
</template>

<script>
    export default {
        name: "thermostat",

        props: {
            step: {
                type: Number,
                default: 1,
            },
        },

        methods: {
            heatUp() {
                this.$emit('heat-up', this.step)
            },

            coolDown() {
                this.$emit('cool-down', this.step)
            },
        }
    }
</script>