<template>
    <div class="h-100 d-flex align-items-center justify-content-center">
        <div class="bg-dark-grey p-5 w-25 rounded-20">

            <div class="row mt-5">
                <div class="col-12 text-center">
                    <Icon :temperature="temperatureNow" class="fa-6x"></Icon>
                </div>
            </div>

            <div class="row mt-5 mb-5">
                <div class="col-12 text-center text-white">
                    <Temperature
                            :value="temperatureNow"
                            :font-weight-bold="false">
                    </Temperature>
                </div>
            </div>

            <div class="row mb-5">
                <div class="col-12 text-center">
                    <Thermostat
                            :step="2"
                            @heat-up="heatUpTemperature"
                            @cool-down="coolDownTemperature">
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
    .bg-dark-grey {
        background-color: #3c3c3c;
    }

    .rounded-20 {
        border-radius: 20px;
    }
</style>
