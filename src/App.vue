<template>
    <div id="app">
        <!-- <img alt="Vue logo" src="./assets/logo.png" /> -->
        <!-- <HelloWorld msg="Welcome to Your Vue.js + TypeScript App" /> -->
        <Header />
        <About />
        <social-media />
    </div>
</template>

<script lang="ts">
import { Component, Vue } from 'vue-property-decorator'
import HelloWorld from './components/HelloWorld.vue'
import Header from './components/Header.vue'
import About from './components/About.vue'
import SocialMedia from './components/SocialMedia.vue'

@Component({
    components: {
        HelloWorld,
        Header,
        About,
        SocialMedia,
    },
})
export default class App extends Vue {}
</script>

<style>
#app {
    font-family: Avenir, Helvetica, Arial, sans-serif;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    text-align: center;
    color: #2c3e50;
    height: 100%;
}

html {
    background: #1b1b1b;
    height: 100%;
}

body {
    height: 100%;
}
</style>
