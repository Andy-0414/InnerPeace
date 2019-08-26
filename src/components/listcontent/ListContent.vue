<template>
	<article class="listcontent">
		<h2>LIST VIEW</h2>
		<hr>
		<p class="listcontent__list">
            <span class="listcontent__list__item">LIST1</span>
            <span class="listcontent__list__item">LIST2</span>
            <span class="listcontent__list__item">LIST3</span>
            <span class="listcontent__list__item">LIST4</span>
            <span class="listcontent__list__item">LIST5</span>
            <span class="listcontent__list__item">LIST6</span>
        </p>
	</article>
</template>

<script>
export default {};
</script>

<style>
.listcontent {
	display: flex;
	flex-direction: column;
	align-items: center;
	padding: 50px;
	width: 100%;
	max-width: 1280px;
	color: white;
	margin: 50px 0;
}
.listcontent h2 {
	font-size: 4em;
	text-align: center;
	font-weight: lighter;
}
.listcontent__list {
    width: 100%;
	font-size: 1.2em;
    display: flex;
    justify-content: center;
    align-items: center;
    flex-wrap: wrap;
}
.listcontent__list__item{
    width: 20%;
    min-width: 200px;
    height: 200px;
    margin: 4% 6%;
    display: flex;
    justify-content: center;
    align-items: center;

    background: linear-gradient(45deg, #7b2ed4, #5050f0);
    border-radius: 5px;
}

@media (min-width: 320px) and (max-width: 480px) {
    .listcontent__list__item{
        width:100%;
        background-color: red !important;
    }
}
</style>