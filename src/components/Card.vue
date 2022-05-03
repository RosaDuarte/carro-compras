<template>
<div class="block m-2" id="menu">
    <div class="card">
        <div class="card-image">
              <img :src="producto.thumbnailUrl" :alt="`imagen-${producto.title}`">
        </div>
        <div class="card-content">
            <h5 class="title is-4">{{producto.title}}</h5>
            <p class="content">$ <span>{{producto.precio}}</span></p>
            <button class="button" @click="agregar(producto)">Comprar</button>
        </div> 
    </div>           
</div>
</template>

<script>
import { useStore } from 'vuex'
export default {
    
    props: ['producto'],
    setup(){
        const store = useStore()
        const agregar=producto=>{
            store.dispatch('agregarAlCarro', producto)
        }
        return{agregar}
    }
}
</script>

<style scoped>
    .block{
        border-radius: 8px;
    }
    h2{
        color: var(--orange);
        font-size: 28px;
        font-weight: 500;
    }
    .card{
        background-color: var(--ocher)
    }
    img{
        width: 220px;
        height: 220px;
        object-fit: cover;
    }
    h5{
        color: var(--dark-grey);
        font-weight: 300;
    }
    p{
        color: var(--dark-grey);
        font-size: 20px;
        font-weight: 500;
    }
    .button{
        font-weight: 700;
        background-color: var(--sand);
        border: 2px solid var( --orange);
        color: var(--dark-grey);
        font-size: 15px;
        position: relative;
        z-index: 1;
        overflow: hidden;
        display: inline-block;
        border-radius: 150px;
    }
    .button:hover{
        color:var(--orange);
    }
    .button::after{
        content: "";
        background: var(--light-grey); /* color de fondo hover */
        position: absolute;
        z-index: -1;
        padding: 16px 20px;
        display: block;
        top: 0;
        bottom: 0;
        left: -100%;
        right: 100%;
        -webkit-transition: all 0.4s;
        transition: all 0.4s;
    }
    .button:hover::after{
        left: 0;
        right: 0;
        top: 0;
        bottom: 0;
        -webkit-transition: all 0.4s;
        transition: all 0.4s;
    }
</style>