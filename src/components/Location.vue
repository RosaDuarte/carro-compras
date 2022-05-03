<template>
    <div class="location-container" id="location">
        <h2>Ubicación</h2>
        <div class="box">
            <iframe src="https://www.google.com/maps/embed?pb=!1m18!1m12!1m3!1d3953.178221123242!2d-72.2226675859012!3d7.770917709562094!2m3!1f0!2f0!3f0!3m2!1i1024!2i768!4f13.1!3m3!1m2!1s0x8e666cbd8a31af4b%3A0xc84fdcd35b8dbb41!2sCalle%2012%20%26%20Carrera%2020%2C%20San%20Crist%C3%B3bal%205001%2C%20T%C3%A1chira!5e0!3m2!1ses!2sve!4v1651431540517!5m2!1ses!2sve" width="600" height="450" style="border:0;" allowfullscreen="" loading="lazy" referrerpolicy="no-referrer-when-downgrade"></iframe>
        </div>
    </div>
</template>

<style scoped>
    .location-container{
        width: 100%;
        height: auto;
        background-color: var(--sand);
    }
    h2{
        color: var(--orange);
        font-size: 35px;
        font-weight: 500;
        padding-top: 20px;
        padding-bottom: 20px;
    }
    .box{
        overflow:hidden;
        padding-bottom:56.25%;
        position:relative;
        height:0;
    }
    .box iframe{
       left:0;
        top:0;
        height:100%;
        width:100%;
        position:absolute;
    }
</style>