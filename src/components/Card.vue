<template>
<div class="block m-2">
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
        border-radius: 5px;
        font-family: Helvetica, sans-serif;
    }
    .card{
        background-color: rgba(255, 255, 255, .8);
    }
    img{
        width: 220px;
        height: 180px;
    }
    h5{
        color: #191934;
    }
    p{
        color: #004b67;
        font-size: 20px;
        font-family: Helvetica, sans-serif;
    }
    .button{
        font-weight: bold;
        background-color: #191934;
        border: 1px solid #004b67;
        color: #d4ceb3;
        font-size: 15px;
        font-family: Helvetica, sans-serif;
        position: relative;
        z-index: 1;
        overflow: hidden;
        display: inline-block;
    }
    .button:hover{
        color:#d4ceb3 ;
    }
    .button::after{
        content: "";
        background: #004b67; /* color de fondo hover */
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