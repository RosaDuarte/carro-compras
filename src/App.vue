<template>
  <Header />
  <Specialties />
  <Location />
  <div class="block">
    <h2>Menú</h2>
     <div class="box is-flex is-flex-direction-row is-flex-wrap-wrap is-justify-content-center">
       <Card
        v-for="producto of productos" :key="producto.id"
        :producto="producto"
        />
     </div>
     <Compras />
  </div>
 <Contact />
</template>

<script>
import {useStore} from 'vuex'
import { computed, onMounted } from '@vue/runtime-core'
import Card from './components/Card'
import Compras from './components/Compras'
import Header from './components/Header'
import Specialties from './components/Specialties'
import Location from './components/Location'
import Contact from './components/Contact'


export default {
  name: 'App',
  components: {
    Card,
    Compras,
    Header,
    Specialties,
    Location,
    Contact
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
    --body: #faf8f4;
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
    background-color: var(--body);
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
  .block h2{
    margin-top: 25px;
    color: var(--orange);
    font-size: 35px;
    font-weight: 500; 
  }
  ::-webkit-scrollbar {
    width: 10px;      
    background-color: var(--body);
  }

  ::-webkit-scrollbar-thumb {
    background: var(--ocher);
    border-radius: 8px;  
  }

  ::-webkit-scrollbar-track {
    background: transparent;
    border-radius: 4px;
    height: 5px;
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
