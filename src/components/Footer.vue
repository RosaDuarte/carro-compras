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