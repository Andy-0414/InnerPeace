<template>
	<article class="information">
		<div ref="background" class="information__background"></div>
        <div ref="logo" class="information__logo">
            <img src="@/assets/logo.png" alt="">
        </div>
	</article>
</template>
<script lang="ts">
import Vue from "vue";
export default Vue.extend({
	mounted() {
        let background: any = this.$refs.background;
        let logo :any = this.$refs.logo;
		for (let i = 0; i < innerWidth/80; i++) {
			let div: HTMLDivElement = document.createElement("div");
			background.appendChild(div);
		}
		addEventListener("mousemove", e => {
			[...background.children].forEach(x => {
                let value = 200-Math.abs(x.offsetLeft-e.clientX);
				x.style.height = `${(value < 0 ? 0 : value)}px`;
			});
            logo.style.transform = `translate3d(${(e.clientX-innerWidth/2)/20}px,${(e.clientY-innerHeight/2)/20}px,0)`;
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

    overflow: hidden;
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
.information__logo{
    position: absolute;
    top: 0;
    left: 0;

    width: 100%;
    height: 100%;

    display: flex;
    justify-content: center;
    align-items: center;
    
    color: white;
    
    transition: 2s cubic-bezier(0.175, 0.885, 0.32, 1.275);
}
.information__logo img{
    width: 20%;
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
