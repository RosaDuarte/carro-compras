<template>
  <tr>
      <th scope="row">{{item.id}}</th>
      <td>{{item.title}}</td>
      <td>{{item.cantidad}}</td>
      <td>
          <span class="icon mr-1" @click="aumentar(item.id)">
            <i class="fas fa-plus-circle is-clickable" id="aumentar"></i>
          </span>
          <span class="icon"  @click="disminuir(item.id)">
            <i class="fas fa-minus-circle is-clickable" id="disminuir"></i>
          </span>
      </td>
      <td>${{item.precio*item.cantidad}}</td>
  </tr>
</template>

<script>
import {useStore} from 'vuex'
export default {
  props: ['item'],
  setup(){
    const store = useStore()
    const aumentar = id=> {store.commit('aumentar', id)}
    const disminuir = id => {store.commit('disminuir', id)}

    return{aumentar, disminuir}
  }
}
</script>

<style>
 #aumentar{
  color:#0d8c00;
 }
 #disminuir{
   color: #e00807;
 }
</style>