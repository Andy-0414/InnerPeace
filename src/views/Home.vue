<template>
	<section class="content">
		<Information></Information>
		<StartContent></StartContent>
		<img class="content__hr" src="../assets/flat line-01.png" alt />
		<TitleContent></TitleContent>
		<img class="content__hr" src="../assets/flat line-01.png" alt />
		<ListContent></ListContent>
	</section>
</template>
<script lang="ts">
import Vue from "vue";
import Information from "@/components/information/Information.vue";
import TitleContent from "@/components/titlecontent/TitleContent.vue";
import StartContent from "@/components/startcontent/StartContent.vue";
import ListContent from "@/components/listcontent/ListContent.vue";
export default Vue.extend({
	components: {
		Information,
		TitleContent,
		StartContent,
		ListContent
	}
});
</script>
<style>
@keyframes bounce {
	0% {
		opacity: 0.5;
	}
	50% {
		opacity: 0.8;
	}
	100% {
		opacity: 0.5;
	}
}
.content {
	display: flex;
	flex-direction: column;
	align-items: center;
	flex-wrap: nowrap;
	overflow-x: hidden;
	background-color: #121319;
}
.content__hr {
	height: 8vh;
	margin: 5%;
	opacity: 0.5;
    animation: bounce 2s infinite;
}
</style>
