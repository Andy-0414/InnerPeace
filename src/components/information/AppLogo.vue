<template>
    <div class="applogo">
        <div class="applogo__logo">
            <img src="../../assets/innerpeace_logo2.png" alt />
        </div>
        <div class="applogo__content">
            <h2 class="applogo__title">
                <span class="applogo__title__animation">I</span>
                <span class="applogo__title__animation">N</span>
                <span class="applogo__title__animation">N</span>
                <span class="applogo__title__animation">E</span>
                <span class="applogo__title__animation" style="margin-right:0.25em;">R</span>
                <span class="applogo__title__animation">P</span>
                <span class="applogo__title__animation">E</span>
                <span class="applogo__title__animation">A</span>
                <span class="applogo__title__animation">C</span>
                <span class="applogo__title__animation">E</span>
            </h2>
            <p class="applogo__text">2019 STA+C 멘탈 케어 솔루션</p>
        </div>
    </div>
</template>
<script lang="ts">
import Vue from "vue";
export default Vue.extend({
    data() {
        return {
            titleElements: [] as any,
            textElement: null as any,
            logoElement: null as any
        };
    },
    mounted() {
        this.titleElements = document.querySelectorAll(
            ".applogo__title__animation"
        );
        this.textElement = document.querySelector(".applogo__text");
        this.logoElement = document.querySelector(".applogo__logo");
        this.titleElements.forEach((x: any, index: number) => {
            x.style.animationDelay = `${index / 4}s`;
            x.style.transitionDelay = `${index / 32}s`;
        });
        var isFade: boolean = false;
        addEventListener("scroll", e => {
            if (scrollY > innerHeight / 3) {
                if (!isFade) {
                    isFade = true;
                    this.titleElements.forEach((x: any) => {
                        x.style.opacity = "0";
                    });
                    this.textElement.style.opacity = "0"
                    this.logoElement.style.opacity = "0"
                }
            } else {
                if (isFade == true) {
                    isFade = false;
                    this.titleElements.forEach((x: any) => {
                        x.style.opacity = "1";
                    });
                    this.textElement.style.opacity = "1"
                    this.logoElement.style.opacity = "1"
                }
            }
        });
    }
});
</script>


<style>
.applogo {
    position: relative;

    width: fit-content;
    height: fit-content;

    display: flex;
    justify-content: center;
    align-items: center;
    align-content: center;
    flex-wrap: wrap;
}
.applogo__logo {
    animation: titleAnimation 4s infinite;
    position: relative;
    z-index: 1;

    width: 200px;
    height: 200px;

    overflow: hidden;

    display: flex;
    justify-content: center;
    align-items: center;

    transition: 0.5s;
}
.applogo__logo img {
    width: 200%;
    height: 200%;
}
.applogo__content {
    margin-top: 3em;
    text-align: right;
}
.applogo__title {
    z-index: 2;
    font-size: 5em;
}
.applogo__title__animation {
    display: inline-block;
    font-family: "NM";
    animation: titleAnimation 4s infinite;
    position: relative;
    top: 0;
    bottom: 0;
    left: 0;
    right: 0;

    text-shadow: -3px 0 #8f665b, 0 3px #8f665b, 3px 0 #8f665b, 0 -3px #8f665b;
    transition: 0.5s;
}
.applogo__text {
    margin-top: 10px;
    font-size: 1.2em;

    transition: 0.5s;
}
@keyframes titleAnimation {
    0% {
        top: 0;
    }
    50% {
        top: 10px;
    }
    100% {
        top: 0;
    }
}
</style>
