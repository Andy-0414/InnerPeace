<template>
	<article class="information">
		<div ref="background" class="information__background"></div>
	</article>
</template>
<script lang="ts">
import Vue from "vue";
export default Vue.extend({
	mounted() {
		let background: any = this.$refs.background;
		for (let i = 0; i < innerWidth/80; i++) {
			let div: HTMLDivElement = document.createElement("div");
			background.appendChild(div);
		}
		addEventListener("mousemove", e => {
			[...background.children].forEach(x => {
                let value = 200-Math.abs(x.offsetLeft-e.clientX);
				x.style.height = `${(value < 0 ? 0 : value)}px`;
			});
        });
        addEventListener("touchmove", e => {
			[...background.children].forEach(x => {
                let value = 200-Math.abs(x.offsetLeft-e.touches[0].clientX);
				x.style.height = `${(value < 0 ? 0 : value)}px`;
			});
		});
	}
});
</script>
<style>
.information {
	position: relative;
	width: 100vw;
	height: 100vh;

	background-color: #121319;
}
.information__background {
	position: absolute;
	top: 0;
	left: 0;

	width: 100%;
	height: 100%;
	overflow: hidden;

	display: flex;
	justify-content: center;
	align-items: flex-end;
}
.information__background div {
	position: relative;
	width: 30px;
	margin: 0 20px;

	background-color: #6a22c6;
	opacity: 0.5;
	transition: 0.5s cubic-bezier(0.175, 0.885, 0.32, 1.275);
}
</style>
