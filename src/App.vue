<template>
	<div id="app" ref="app">
		<router-view />
		<div ref="scrollBar" class="scrollBar"></div>
	</div>
</template>
<script lang="ts">
import Vue from "vue";
export default Vue.extend({
	mounted() {
		this.resizing();
		addEventListener("resize", e => {
			this.resizing();
		});
		addEventListener("scroll", e => {
			(this.$refs.scrollBar as HTMLDivElement).style.top =
				(innerHeight /
					(this.$refs.app as HTMLDivElement).offsetHeight) *
					scrollY +
				"px";
		});
	},
	methods: {
		resizing() {
			(this.$refs.scrollBar as HTMLDivElement).style.height =
				(innerHeight /
					(this.$refs.app as HTMLDivElement).offsetHeight) *
					innerHeight +
				"px";
		}
	}
});
</script>

<style>
* {
	margin: 0;
	padding: 0;
	box-sizing: border-box;
	font-family: "Noto Sans KR", sans-serif;
	scroll-behavior: smooth;
	letter-spacing: 0.1em;
	line-height: 1.5em;
}
hr {
	width: 30%;
	height: 5px;
	border: none;
	background: linear-gradient(45deg, #7b2ed4, #5050f0);
	margin-top: 20px;
	margin-bottom: 40px;
}
h2 {
	text-shadow: 0px 0px 20px #5050f0;

	transition: 0.2s;
}
h2:hover {
	text-shadow: 0px 0px 10px #5050f0;
}
#app {
	width: 100vw;
	height: auto;
}
.scrollBar {
	position: fixed;
	right: 0;
	top: 0;

	width: 5px;
	height: 10px;

	border-radius: 10px;

	background-color: rgba(0, 0, 0, 0.5);
	transition: 0.5s cubic-bezier(0.175, 0.885, 0.32, 1.275);
}
::-webkit-scrollbar {
	display: none;
}
@media (min-width: 320px) and (max-width: 480px) {
    hr{
        width: 80%;
    }
}
</style>
