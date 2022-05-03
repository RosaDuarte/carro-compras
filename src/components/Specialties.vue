<template>
    <section class="specialties">
        <div class="specialties-container">
            <h2>Especialidades</h2>
            <div>
                <span>
                    <img src="@/assets/pollo-asado.png" alt="">
                </span>
                <span>
                    <img src="@/assets/churrasco.png" alt="">
                </span>
                <span>
                    <img src="@/assets/pizza.png" alt="">
                </span>
                <span>
                    <img src="@/assets/hotdog.png" alt="">
                </span>
                <span>
                    <img src="@/assets/burger.png" alt="">
                </span>   
            </div>
        </div>
    </section>
</template>


<style scoped>
    .specialties{
        width: 100%;
        height: auto;
        background-color: var(--body);
    }
    .specialties-container{
        padding-top: 18px;
        text-align: center;
        margin: auto;
        height: 300px;
    }
    h2{
        margin-top: 15px;
        color: var(--orange);
        font-size: 35px;
        font-weight: 500;
    }
    .specialties-container div{
        width: 50%;
        min-width: 290px;
        display: flex;
        justify-content: center;
        flex-wrap: wrap;
        margin: auto;
        padding-top: 20px;
    }
    .specialties-container div span{
        margin: 15px;
    }
    .specialties-container span img{
        width: 60px;
        height: 60px;
    }

    @media (min-width: 1024px) {
        .specialties-container{
            height: 220px;
        }
    }

</style>