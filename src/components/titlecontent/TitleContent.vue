<template>
	<article class="titlecontent">
		<div class="titlecontent__content">
			<h2>TITLE</h2>
			<hr />
			<p class="titlecontent__content__text">CONTENT</p>
			<div class="titlecontent__sub">
				<img class="titlecontent__img" src="../../assets/screen1.png" />
				<div>
					<h3>Sub Title</h3>
					<p>Lorem ipsum dolor sit amet consectetur adipisicing elit. Nihil inventore necessitatibus maxime natus repellat tempora perspiciatis quis placeat illo, officiis mollitia animi reiciendis. Quasi consequatur corporis quia aspernatur enim. Assumenda.</p>
					<p>
						<img class="titlecontent__subimg" src="../../assets/logo.png" alt />
						<img class="titlecontent__subimg" src="../../assets/logo.png" alt />
						<img class="titlecontent__subimg" src="../../assets/logo.png" alt />
						<img class="titlecontent__subimg" src="../../assets/logo.png" alt />
					</p>
					<p>
						<button>BUTTON</button>
					</p>
				</div>
			</div>
		</div>
	</article>
</template>

<script>
export default {};
</script>

<style>
.titlecontent {
	display: flex;
	align-items: center;
	padding: 50px;
	width: 100%;
	max-width: 1280px;
}
.titlecontent__content {
	color: white;
	display: flex;
	flex-direction: column;
	align-items: center;
	width: 100%;
}
.titlecontent__content > h2 {
	font-size: 4em;
	text-align: center;
	font-weight: lighter;
}
.titlecontent__content__text {
	font-size: 1.2em;
	width: 80%;

	word-wrap: break-word;
	text-align: center;
}
.titlecontent__sub {
	margin-top: 100px;
	width: 100%;
	display: flex;
	justify-content: center;
	align-items: center;
}
.titlecontent__img {
	width: 30%;
	border-radius: 20px;
	margin-right: 40px;

	box-shadow: 0px 0px 20px rgba(123, 46, 212, 0.2);
}
.titlecontent__sub div {
	width: 100%;
	display: flex;
	flex-direction: column;
	align-items: center;
	justify-content: center;
}
.titlecontent__sub h3 {
	font-size: 3em;
	font-weight: lighter;
	text-align: right;
	width: 80%;
}
.titlecontent__sub p {
	margin-top: 10px;
	text-align: right;
	width: 80%;
	font-size: 1.2em;
}
.titlecontent__sub button {
	cursor: pointer;
	background: linear-gradient(45deg, #7b2ed4, #5050f0);
	border: none;
	outline: none;
	border-radius: 10px;
	color: white;
	font-size: 1em;
	margin-top: 50px;
	padding: 10px 100px;
	transition: 0.5s cubic-bezier(0.175, 0.885, 0.32, 1.275);
}
.titlecontent__sub button:hover {
	transform: scale(1.1);
}
.titlecontent__subimg {
	margin-top: 40px;
	width: 25%;
}

@media (min-width: 320px) and (max-width: 480px) {
	.titlecontent__content__text {
		width: 100%;
	}
	.titlecontent__sub {
		flex-direction: column;
	}
	.titlecontent__sub h3 {
		text-align: left;
		width: 100%;
	}
	.titlecontent__sub p {
		text-align: left;
		width: 100%;
	}
	.titlecontent__img {
		width: 100%;
		margin-right: 0;
		margin-bottom: 50px;
	}
	.titlecontent__sub button {
		padding: 10px 0;
		width: 100%;
	}
}
</style>