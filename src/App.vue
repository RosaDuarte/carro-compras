<template>
  <Header />
  <Specialties />
  <div class="block">
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
import Header from './components/Header'
import Specialties from './components/Specialties'


export default {
  name: 'App',
  components: {
    Card,
    Compras,
    Header,
    Specialties
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
  :root{
    --beige: #ede7db;
    --sand: #e8dccc;
    --dark-beige: #e8dccc;
    --light-grey: #a7b2b6;
    --dark-grey: #696d6c;
    --ocher: #e8c083;
    --orange: #d27947;
  }
  *{
    padding: 0;
    margin: 0;
    box-sizing: border-box;
  }
  #app{
    width: 100%;
    font-family: 'Roboto', sans-serif;
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
