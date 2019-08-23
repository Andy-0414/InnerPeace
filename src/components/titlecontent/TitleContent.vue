<template>
	<article class="titlecontent">
		<div class="titlecontent_content">
			<h2>TITLE</h2>
			<hr />
			<p>
				<img class="titlecontent_img" src="../../assets/screen1.png" />
				Lorem ipsum dolor sit amet consectetur, adipisicing elit. Sequi repudiandae doloremque eligendi blanditiis consequuntur dolor aliquam quos magnam a quasi ipsa et sint at, quo repellendus magni incidunt obcaecati ad.
			</p>
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
.titlecontent_img {
	float: left;
	width: 20%;
    margin-right: 30px;
    margin-bottom: 30px;

	border-radius: 5px;
}
.titlecontent_content {
	color: white;
	display: flex;
	flex-direction: column;
	align-items: center;
	width: 100%;
}
.titlecontent_content h2 {
	font-size: 4em;
	font-weight: lighter;
}
.titlecontent_content p {
    display: flex;
    align-items: center;
	font-size: 1.2em;
}
</style>