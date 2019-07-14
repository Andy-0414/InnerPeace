<template>
    <div id="app">
        <header id="header">
            <h1 class="header__title">INNER PEACE</h1>
            <nav id="header__nav">
                <li class="header__nav__item">ITEM1</li>
                <li class="header__nav__item">ITEM2</li>
                <li class="header__nav__item">ITEM3</li>
            </nav>
        </header>
        <router-view />
    </div>
</template>

<style>
@font-face { font-family: "NM"; src: url("./assets/NanumMyeongjo.ttf");}
* {
    margin: 0;
    padding: 0;

    box-sizing: border-box;

    font-family: 'Nanum Gothic', sans-serif;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    /* color: #8f665b; */
    color: white;

    list-style: none;
}
#app{
    overflow-x: hidden;
    height: 5000px;
}
#header {
    z-index: 100;

    position: fixed;
    top: 0;
    left: 0;

    width: 100%;
    height: 70px;

    display: flex;
    align-items: center;
    justify-content: space-between;

    padding: 0 60px;
}
#header__nav {
    display: flex;
}
.header__title{
    font-family: "NM"
}
.header__nav__item{
    margin-left: 10px;
}
</style>
