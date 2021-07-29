<template>
    <div id="test-main">
        <button id="test-button" @click="show = !show">Show</button>
        <transition name="fade">
            <p id="title" v-if="show">{{ title }}</p>
        </transition>
        <transition name="fade">
            <button id="contact-button" v-if="show">Contact</button>
        </transition>
    </div>
</template>
<script lang="ts">
import { Component, Vue } from 'vue-property-decorator'

@Component
export default class TestComponent extends Vue {
    title = 'Hi, I am the Globbo Glabala.'
    show = false

    mounted(): void {
        this.show = true
    }
}
</script>

<style scoped>
#contact-button {
    border-radius: 30px;
    color: white;
    padding: 10px 20px;
    border: 2px solid #fe0000;
    background: #1b1b1b;
    font-family: 'Consolas';
    font-size: 15px;
    /* transition: all 0.7s; */
}

/* #contact-button:hover{
    background-color: #fe0000;
    font-size:17px;
} */

#test-button {
    display: none;
}

#title {
    font-family: 'Consolas';
    font-size: 40px;
    color: white;
    margin-top: 5%;
}

/*TRANSITIONS*/
.fade-enter {
    opacity: 0;
}

.fade-enter-to {
    opacity: 1;
    transition: opacity 2s;
}

.fade-leave-to {
    opacity: 0;
    transition: opacity 2s;
}
</style>
