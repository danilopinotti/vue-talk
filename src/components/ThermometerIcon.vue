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
                    return ['fa-thermometer-full', 'text-danger'];

                if (this.temperature >= 30)
                    return ['fa-thermometer-three-quarters', 'text-warning'];

                if (this.temperature >= 20)
                    return ['fa-thermometer-half', 'text-primary'];

                if (this.temperature >= 10)
                    return ['fa-thermometer-quarter', 'text-info'];

                return ['fa-thermometer-empty', 'text-white'];
            }
        }
    }
</script>

<style scoped>

</style>