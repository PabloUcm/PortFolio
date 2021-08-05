<template>
    <div id="about-main">
        <div id="about-parent">
            <transition name="about1">
                <div v-if="show" class="about-box" id="about1">
                    <h2>About 1</h2>
                </div>
            </transition>
            <transition name="about2">
                <div v-if="show" class="about-box" id="about2">
                    <h2>About 1</h2>
                </div>
            </transition>
        </div>
    </div>
</template>
<script>
import { Component, Vue } from 'vue-property-decorator'

@Component
export default class About extends Vue {
    show = false

    mounted() {
        this.show = true
    }
}
</script>
<style scoped>
#about-main {
    margin-top: 0%;
    height: 50%;
}

#about-parent {
    display: flex;
    justify-content: space-evenly;
    height: 100%;
}

.about-box {
    color: white;
    font-family: 'Consolas';
    border: solid 3px #0096d2;
    padding: 20px;
    width: 30%;
    height: 90%;
    margin: 10% 0%;
}

/*TRANSITIONS*/
.about1-enter {
    opacity: 0;
    transform: translateX(-60px);
}

.about2-enter {
    opacity: 0;
    transform: translateX(60px);
}

.about1-enter-to {
    opacity: 1;
    transition: all 2s;
}

.about2-enter-to {
    opacity: 1;
    transition: all 2s;
}

.about1-leave-to {
    opacity: 0;
}

.about2-leave-to {
    opacity: 0;
}
</style>
