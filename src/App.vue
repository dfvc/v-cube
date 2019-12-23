<template>
    <div id="app">
        <section class="cubes-holder">
            <v-cube 
                v-for="(cube, index) in cubes"
                :key="index"
                :edge-size="cube.edgeSize"
                :show-edge="cube.showEdge"
                :rotation-duration="cube.rotationDuration"
                :rotation-step="cube.rotationStep"
                :auto-rotate="cube.autoRotate"
                :auto-rotate-delay-factor="cube.autoRotateDelayFactor"
            />
        </section>
    </div>
</template>

<script>
    import VCube from './components/VCube.vue'

    export default {
        name: 'app',

        components: {
            VCube
        },

        data() {
            return {
                cubes: [
                    {
                        edgeSize: 100, 
                        showEdge: false, 
                        rotationDuration: 300,
                        rotationStep: 90,
                        autoRotate: true, 
                        autoRotateDelayFactor: 3,
                    }
                ]
            }
        },
    }
</script>


<style lang="scss">
    * {
        box-sizing: border-box;
    }

    html, 
    body {
        height: 100%;
    }

    body {
        background-color: $primary-light;
        font-family: sans-serif;
    }

    .cubes-holder {
        display: flex;
        justify-content: center;
        align-items: center;
        flex-wrap: wrap;
        margin: 0 auto;
        max-width: 1024px;
    }
</style>

