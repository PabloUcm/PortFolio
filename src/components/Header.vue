<template>
    <div id="header-main">
        <div id="lang-header">
            <span class="lang-row" @click="changeLang(-1)">&lt;</span>
            <transition name="fadeLang" mode="out-in">
                <!-- <p id="lang-name">{{ langList[selectedLang] }}</p> -->
                <p class="lang-name" v-if="langList[selLang] === 'ES'" :key="1">
                    ES
                </p>
                <p class="lang-name" v-else :key="2">EN</p>
            </transition>
            <transition name="fadeLang" mode="out-in">
                <!-- <img
                    id="flag"
                    v-bind:src="
                        require(`../assets/${langList[selLang]}-flag.png`)
                    "
                /> -->
                <img
                    class="flag"
                    v-if="langList[selLang] === 'ES'"
                    :key="`img-1`"
                    v-bind:src="require(`../assets/ES-flag.png`)"
                />
                <img
                    class="flag"
                    v-else
                    :key="`img-2`"
                    v-bind:src="require(`../assets/EN-flag.png`)"
                />
            </transition>
            <span class="lang-row" @click="changeLang(1)">&gt;</span>
        </div>
        <div id="title-section">
            <button id="test-button" @click="show = !show">Show</button>
            <transition name="fade">
                <p id="title" v-if="show">{{ title }}</p>
            </transition>
            <transition name="fade">
                <button id="contact-button" v-if="show">Contact</button>
            </transition>
        </div>
    </div>
</template>
<script lang="ts">
import { Component, Vue } from 'vue-property-decorator'

@Component
export default class TestComponent extends Vue {
    title = 'Hi, I am the Globbo Glabala.'
    show = false
    selLang = 0
    langList = ['ES', 'EN']

    changeLang(step: number): void {
        if (this.selLang + step === this.langList.length) {
            this.selLang = 0
        } else if (this.selLang + step < 0) {
            this.selLang = this.langList.length - 1
        } else {
            this.selLang += step
        }
    }

    mounted(): void {
        this.show = true
    }
}
</script>

<style scoped>
.lang-name {
    width: 2%;
}

.lang-row {
    margin: 0px 1%;
    font-weight: bolder;
    font-size: 18px;
    transition: all 0.2s;
    color: #00aae4;
}

.lang-row:hover {
    transform: scale(1.5);
    cursor: pointer;
}

.flag {
    width: 20px;
    height: 20px;
    margin-left: 5px;
}

#lang-header {
    display: flex;
    justify-content: flex-end;
    align-items: center;
    margin-right: 10%;
    color: white;
}

#contact-button {
    border-radius: 30px;
    color: white;
    padding: 10px 20px;
    border: 2px solid #0096d2;
    background: #1b1b1b;
    font-family: 'Consolas';
    font-size: 15px;
    /* transition: all 0.7s; */
}

#contact-button:hover {
    /* background-color: #fe0000;
    font-size:17px; */
    cursor: pointer;
}

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
    transition: opacity 1.4s;
}

.fade-leave-to {
    opacity: 0;
    transition: opacity 1.4s;
}

.fadeLang-enter {
    opacity: 0;
    transform: scale(0);
}

.fadeLang-enter-to {
    opacity: 1;
    transform: scale(1);
    transition: all 0.4s;
}

.fadeLang-leave-to {
    opacity: 0;
    transform: scale(0);
    transition: all 0.4s;
}
</style>
