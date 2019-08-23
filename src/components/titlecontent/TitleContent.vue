<template>
	<article id="content" class="titlecontent">
		<img class="titlecontent_img" src="../../assets/logo.png" />
		<div class="titlecontent_content">
			<h2>TITLE</h2>
			<p>Lorem ipsum dolor sit amet consectetur, adipisicing elit. Sequi repudiandae doloremque eligendi blanditiis consequuntur dolor aliquam quos magnam a quasi ipsa et sint at, quo repellendus magni incidunt obcaecati ad.</p>
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
.titlecontent_img{
    width: 20%;
}
.titlecontent_content{
    color: #7b2ed4;
    width: 80%;
    text-align: right;
}
</style>