<template>
    <i class="fa" :class="iconClasses"></i>
</template>

<script>
    export default {
        name: "ThermometerIcon",

        props: {
            temperature: Number,
        },

        computed: {
            iconClasses() {
                if (this.temperature >= 45)
                    return ['fa-temperature-high', 'text-danger'];

                if (this.temperature >= 30)
                    return ['fa-thermometer-three-quarters', 'text-warning'];

                if (this.temperature >= 20)
                    return ['fa-thermometer-half', 'text-white'];

                if (this.temperature >= 10)
                    return ['fa-thermometer-quarter', 'text-primary'];

                return ['fa-temperature-low', 'text-info'];
            }
        }
    }
</script>

<style scoped>

</style>