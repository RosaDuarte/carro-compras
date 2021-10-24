<template>
  <div class="block">
    <div class="title-block">
      <h1 class="title is-2 pt-3">Tus compras de comida</h1>
    </div>  
     <div class="box is-flex is-flex-direction-row is-flex-wrap-wrap is-justify-content-center">
       <Card
        v-for="producto of productos" :key="producto.id"
        :producto="producto"
        />
     </div>
     <Compras />
  </div>
 
</template>

<script>
import {useStore} from 'vuex'
import { computed, onMounted } from '@vue/runtime-core'
import Card from './components/Card'
import Compras from './components/Compras'


export default {
  name: 'App',
  components: {
    Card,
    Compras
  },
  setup(){
    const store = useStore()
    onMounted(()=>{
      store.dispatch('fetchData')
    })

    const productos = computed(()=> store.state.productos)
    

    return {productos}
  }
}
</script>

<style>
  html{
    width: 100%;
    background-attachment: fixed;
    background-position: center center;
    background-repeat: no-repeat;
    background-size: cover;
    background-image: url(./assets/fondo.jpg);
  }
  body{
    font-family: Helvetica, sans-serif;
    text-align: center;
    box-sizing: border-box;
  }
  .title-block{
    background-color: rgba(237, 220, 151, .5);
    padding-top: 10px;
  }
  .block h1{
    text-align: center;
    padding-bottom: 15px;
    -webkit-text-fill-color: #004b67;
  }
  .box{
    background-color: transparent;
  }

  @media (min-width:1216px) and (max-width:1407px) {
    .box{
      width: 90%;
      margin: auto;
    }
  }

  @media (min-width:1408px){
    .box{
      width: 80%;
      margin: auto;
    }
  }
 
</style>
