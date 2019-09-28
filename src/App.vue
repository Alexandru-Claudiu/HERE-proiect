<template>
    <div id="app">
        <div style="padding: 10px 0">
            <div>
                <label style="display: inline-block; width: 60px; color: #FFF">Start</label>
                <input type="text" v-model="start" />
            </div>
            <div>
                <label style="display: inline-block; width: 60px; color: #FFF">Finish</label>
                <input type="text" v-model="finish" />
            </div>
            <button type="button" v-on:click="route()">Route</button>
        </div>
        <HereMap ref="map" appId="fb8OVkOGZBCgAAGvHpu9" appCode="D5Li-I6ki6fibXkm8hPHMr0Bol8lVIb7yle8Ll7zJNs" lat="45.760696" lng="21.226788" width="60" height="530px" />
    </div>
</template>

<script>
    import HereMap from "./components/HereMap.vue"

    export default {
        name: 'app',
        components: {
            HereMap
        },
        data() {
            return {
                start: "",// 45.759770,21.256930  mall
                finish: "" //45.732830,21.267580  str siemens
            }
        },
        methods: {
            route() {
                this.$refs.map.route(this.start, this.finish);
            }
        }
    }
</script>

<style>
    body {
        margin: 20px;
        background-color: #1d232d;
    }
</style>



