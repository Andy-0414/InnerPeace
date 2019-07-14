<template>
    <article class="information">
        <div class="information__background"></div>
        <app-logo class="information_applogo" />
    </article>
</template>
<script lang="ts">
import Vue from "vue";
import AppLogo from "./AppLogo.vue";

export default Vue.extend({
    mounted(){
        let background:any = document.querySelector(".information__background")
        addEventListener('scroll',e=>{
            background.style.backgroundPositionY = `-${scrollY/2}px`
        })
    },
    components: {
        AppLogo
    }
});
</script>

<style>
.information {
    width: 100vw;
    height: 100vh;
    /* background: linear-gradient(to bottom, #fcdbd1, #ffffff); */
    /* background-image: url("../../assets/innerpeace_text.png"); */
    background-position: center;
    background-size: cover;

    display: flex;
    justify-content: center;
    align-items: center;

    padding: 50px;
}
.information__background {
    position: absolute;
    top: 0;
    left: 0;

    width: 100%;
    height: 100%;

    opacity: 0.9;
    filter: brightness(20%);
    background-image: url("../../assets/background.png");
    background-size: cover;
    background-attachment: fixed;

    display: flex;
    justify-content: center;
    align-items: center;
    overflow: hidden;
}
.information_applogo {
    width: 100%;
    height: 100%;
}
</style>
