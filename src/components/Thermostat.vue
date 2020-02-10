<template>
    <span>
        <button class="btn btn-danger btn-md" @click="heatUp">
            <i class="fa fa-fire"></i>
        </button>
        <button class="btn btn-info btn-md" @click="coolDown">
            <i class="fa fa-snowflake"></i>
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
                this.$emit('heatUp', this.step)
            },

            coolDown() {
              this.$emit('coolDown', this.step)
            },
        }
    }
</script>

<style scoped>

</style>