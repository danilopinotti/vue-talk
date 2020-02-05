<template>
    <div class="pt-5">
        <div class="row">
            <div class="col-12">
                <Temperature
                        :value="temperatureNow"
                        :measure-unit="'Celcius'">
                </Temperature>

                <Icon :temperature="temperatureNow" class="fa-2x"></Icon>
            </div>
        </div>

        <div class="row">
            <div class="col-12">
                <Thermostat
                        :step="3"
                        @heatUp="heatUpTemperature"
                        @coolDown="coolDownTemperature">
                </Thermostat>
            </div>
        </div>
    </div>
</template>

<script>
    import Temperature from "./Temperature";
    import Thermostat from "./Thermostat";
    import ThermometerIcon from "./ThermometerIcon";

    export default {
        name: 'Home',

        components: {
            Thermostat,
            'Temperature': Temperature,
            'Icon': ThermometerIcon,
        },

        data() {
            return {
                temperatureNow: 10,
            }
        },

        methods: {
            heatUpTemperature(addedTemperature) {
                this.temperatureNow += addedTemperature;
            },

            coolDownTemperature(removedTemperature) {
                this.temperatureNow -= removedTemperature;
            },
        },
    }
</script>

<style scoped>
</style>
