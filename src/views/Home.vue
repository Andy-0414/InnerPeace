<template>
    <section class="content">
        <Information></Information>
        <StartContent></StartContent>
        <TitleContent></TitleContent>
    </section>
</template>
<script lang="ts">
import Vue from "vue";
import Information from "@/components/information/Information.vue";
import TitleContent from "@/components/titlecontent/TitleContent.vue";
import StartContent from "@/components/startcontent/StartContent.vue";
export default Vue.extend({
    components: {
        Information,
        TitleContent,
        StartContent
    }
});
</script>
<style>
.content{
    display: flex;
    flex-direction: column;
    align-items: center;
    flex-wrap: nowrap;
    overflow-x: hidden;
    background-color: #121319;
}
</style>
