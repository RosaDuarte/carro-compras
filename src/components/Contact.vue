<template>
    <div class="contact-container" id="contact">
        <span class="img"></span>
        <h2>Contacto</h2>
        <div class="box">
            <span>
                <i class="fa-brands fa-instagram"></i>
            </span>
            <span>
                <i class="fa-brands fa-facebook"></i>
            </span>
            <span>
                <i class="fa-brands fa-tiktok"></i>
            </span>
            <span>
                <i class="fa-brands fa-whatsapp"></i>
            </span>
        </div>
    </div>
</template>


<style scoped>
    .contact-container{
        width: 100%;
        background-color: var(--body);
        position: relative;
    }
    .contact-container .img{
        background-image: url(@/assets/pepper.png);
        background-repeat: no-repeat;
        background-position: left;
        background-size: cover;
        width: 100px;
        height: 50px;
        position: absolute;
        left: calc(50% - 55px);
        top: -60px;
        
    }
    .contact-container h2{
        color: var(--orange);
        font-size: 35px;
        font-weight: 500;
    }
    .contact-container span{
        margin: 8px;
    }
    .contact-container span i{
        font-size: 45px;
        color: var(--dark-grey);
        cursor: pointer;
    }
    .contact-container span i:hover{
        color: var(--orange);
        transition: color 0.4s;
    }
</style>