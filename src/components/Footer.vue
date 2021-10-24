<template>
  <th scope="row" colspan="2">Total de productos</th>
  <td>{{total}}</td>
  <td>
      <button class="button" @click="vaciar">Vaciar todo</button>
  </td>
  <td>$ <span>{{totalPrecio}}</span></td>
</template>

<script>
import { computed } from '@vue/reactivity'
import {useStore} from 'vuex'
export default {
  setup(){
    const store = useStore()
    const total = computed(()=> store.getters.totalCantidad)
    const totalPrecio= computed(()=> store.getters.totalPrecio)
    const vaciar = ()=> {store.commit('vaciarCarrito')}

    return {total, totalPrecio, vaciar}
  }
}
</script>

<style scoped>
  .button{
        background-color: #191934;
        border: 1px solid #004b67;
        color: #d4ceb3;
        font-size: 15px;
        font-weight: bold;
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