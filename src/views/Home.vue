<template>
    <section class="content">
        <Information></Information>
        <TitleContent></TitleContent>
    </section>
</template>
<script lang="ts">
import Vue from "vue";
import Information from "@/components/information/Information.vue";
import TitleContent from "@/components/titlecontent/TitleContent.vue";
export default Vue.extend({
    components: {
        Information,
        TitleContent
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
}
</style>
