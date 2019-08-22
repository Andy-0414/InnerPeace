<template>
	<article class="information">
		<div ref="circlebackground" class="information__background__circle"></div>
		<div ref="background" class="information__background"></div>
		<div ref="logo" class="information__logo">
			<img src="@/assets/logo.png" alt />
			<button class="information__logo__button">More ></button>
		</div>
		<div ref="cursor" class="cursor"></div>
	</article>
</template>
<script lang="ts">
import Vue from "vue";
export default Vue.extend({
	mounted() {
		let circlebackground: any = this.$refs.circlebackground;
		let logo: any = this.$refs.logo;
		let cursor: any = this.$refs.cursor;
		for (let i = 0; i < innerWidth / 100; i++) {
			let size = (Math.random() * innerHeight) / 2 + innerHeight / 4;
			let positionX =
				Math.random() * (innerWidth + innerWidth / 4) - innerWidth / 4;
			let positionY =
				Math.random() * (innerHeight + innerHeight / 4) -
				innerHeight / 4;
			let div2: any = document.createElement("div");
			div2.style.transform = `translate3d(${positionX}px,${positionY}px,0)`;
			div2.style.width = `${size}px`;
			div2.style.height = `${size}px`;
			div2.controller = {
				position: [positionX, positionY],
				size: size
			};
			div2.style.transition =
				size / (innerHeight / 4) +
				"s cubic-bezier(0.175, 0.885, 0.32, 1.0)";
			div2.style.animation = `moving ${size /
				(innerHeight / 16)}s infinite`;

			circlebackground.appendChild(div2);
		}
		addEventListener("scroll", e => {
			[...circlebackground.children].forEach(x => {
				x.style.top = scrollY / 2 + "px";
			});
		});
		this.$el.addEventListener("mousemove", (e: any) => {
			cursor.style.transform = `translate3d(${e.clientX-20}px,${e.clientY-20+scrollY}px,0)`;
			[...circlebackground.children].forEach(x => {
				x.style.transform = `translate3d(${x.controller.position[0] +
					((e.clientX - innerWidth / 2) / x.controller.size) *
						20}px,${x.controller.position[1] +
					((e.clientY - innerHeight / 2) / x.controller.size) *
						20}px,0)`;
			});
			logo.style.transform = `translate3d(${(e.clientX - innerWidth / 2) /
				20}px,${(e.clientY - innerHeight / 2) / 20}px,0)`;
		});
		this.$el.addEventListener("touchmove", (e: any) => {
			[...circlebackground.children].forEach(x => {
				x.style.transform = `translate3d(${x.controller.position[0] +
					((e.touches[0].clientX - innerWidth / 2) /
						x.controller.size) *
						20}px,${x.controller.position[1] +
					((e.touches[0].clientY - innerHeight / 2) /
						x.controller.size) *
						20}px,0)`;
			});
			logo.style.transform = `translate3d(${(e.touches[0].clientX -
				innerWidth / 2) /
				20}px,${(e.touches[0].clientY - innerHeight / 2) / 20}px,0)`;
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

	cursor: none;
}
.cursor {
	position: absolute;

	top: 0;
	left: 0;

	width: 40px;
	height: 40px;

    line-height: 0em;

	display: flex;
	justify-content: center;
	align-items: center;

	border: 3px solid #5050f0;
	border-radius: 100%;

	color: #5050f0;
	font-size: 2em;
	font-weight: bold;

	z-index: 9;
	transition: 0.5s cubic-bezier(0.175, 0.885, 0.32, 1);
}
@keyframes moving {
	0% {
		left: 0;
	}
	50% {
		left: 1%;
	}
	100% {
		left: 0;
	}
}
.information__background__circle {
	position: absolute;
	top: 0;
	left: 0;

	width: 100%;
	height: 100%;
	overflow: hidden;
}
.information__background__circle div {
	position: absolute;

	background: linear-gradient(45deg, #7b2ed4, #5050f0);
	filter: blur(5px);
	opacity: 0.2;
	border-radius: 100%;
}
.information__logo {
	position: absolute;
	top: 0;
	left: 0;

	width: 100%;
	height: 100%;

	display: flex;
	flex-direction: column;
	justify-content: center;
	align-items: center;

	color: white;
	opacity: 0.8;

	transition: 2s cubic-bezier(0.175, 0.885, 0.32, 1.275);

	z-index: 10;
}
.information__logo img {
	height: 30%;
}
.information__logo__button {
	cursor: pointer;
	outline: none;

	font-size: 1.2em;
	font-weight: bold;
	color: white;

	border: none;
	padding: 10px 100px;
	margin-top: 50px;
	border-radius: 12px;
	background: linear-gradient(45deg, #7b2ed4, #5050f0);
	transition: 1s cubic-bezier(0.175, 0.885, 0.32, 1.275);
}
.information__logo__button:hover {
	transform: scale(1.1);
}
</style>
