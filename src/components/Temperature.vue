<template>
    <span>
        {{value}}º
        {{measureUnit}}
    </span>
</template>

<script>
    export default {
        name: "Temperature",

        props: {
            value: Number,

            measureUnit: {
                required: false,
                default: 'Celcius',
                validator: function (value) {
                    const validUnits = ['Celcius', 'Fahrenheit'];
                    return validUnits.indexOf(value) !== -1
                }
            },
        }
    }
</script>

<style scoped>

</style>