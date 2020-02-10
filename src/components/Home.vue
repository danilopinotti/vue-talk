<template>
    <div class="h-100 d-flex align-items-center justify-content-center">
        <div class="bg-black-transparent p-5">

            <div class="row">
                <div class="col-12 text-center">
                    <Icon :temperature="temperatureNow" class="fa-6x"></Icon>
                </div>
            </div>

            <div class="row mt-2">
                <div class="col-12 text-center text-white">
                    <Temperature
                            :value="temperatureNow"
                            :measure-unit="'Celcius'">
                    </Temperature>
                </div>
            </div>

            <div class="row mt-5 mb-0">
                <div class="col-12 text-center">
                    <Thermostat
                            :step="3"
                            @heatUp="heatUpTemperature"
                            @coolDown="coolDownTemperature">
                    </Thermostat>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
    import Thermostat from "./Thermostat";
    import Temperature from "./Temperature";
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

<style>
    body {
        background-position-x: 0;
        background-image: url('../assets/bg-trees.jpg');
        background-size: 100% 100%;
    }

    .bg-black-transparent {
        background-color: rgba(0, 0, 0, 0.60);
    }
</style>
