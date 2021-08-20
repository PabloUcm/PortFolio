<template>
    <div id="social-main">
        <ul id="social-list">
            <transition name="social-media-left">
                <li v-if="show" class="social-box">
                    <div class="media-icon">
                        <img
                            class="media-img"
                            src="../assets/github-icon.png"
                        />
                    </div>
                    <span> GitHub </span>
                </li>
            </transition>
            <transition name="social-media-right">
                <li v-if="show" class="social-box">
                    <div class="media-icon">
                        <img
                            class="media-img"
                            src="../assets/linkedin-icon.png"
                        />
                    </div>
                    <span> Linkedin </span>
                </li>
            </transition>
            <transition name="social-media-left">
                <li v-if="show" class="social-box">
                    <div class="media-icon">
                        <img class="media-img" src="../assets/email-icon.png" />
                    </div>
                    <span> Email </span>
                </li>
            </transition>
        </ul>
    </div>
</template>

<script>
import { Component, Vue } from 'vue-property-decorator'

@Component
export default class SocialMedia extends Vue {
    show = false

    mounted() {
        this.show = true
    }
}
</script>

<style scoped>
#social-main {
    margin-top: 10%;
}

#social-list {
    color: white;
    font-family: 'Consolas';
    list-style: none;
    display: flex;
    flex-direction: column;
    align-items: center;
}

.social-box {
    border: 2px solid #0096d2;
    border-radius: 60px;
    margin: 10px 0px;
    padding: 20px;
    width: 60%;
    /* background-color: #0096d2; */
    display: flex;
    align-items: center;
}

.media-icon {
    /* border: 2px solid black; */
    border-radius: 100px;
    padding: 10px;
    margin-right: 25px;
}

.media-img {
    height: 40px;
    width: 40px;
}

.social-media-left-enter {
    opacity: 0;
    transform: translateX(-90px);
}

.social-media-right-enter {
    opacity: 0;
    transform: translateX(90px);
}

.social-media-left-enter-to {
    opacity: 1;
    transition: all 2s;
}

.social-media-right-enter-to {
    opacity: 1;
    transition: all 2s;
}

.social-media-left-leave-to {
    opacity: 0;
}

.social-media-right-leave-to {
    opacity: 0;
}
</style>
