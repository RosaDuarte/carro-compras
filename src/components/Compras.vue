<template>
  <div class="table-container" id="shopping">
      <div class="title-container block">
          <h2 class="title is-3">Tu compra</h2>
      </div>
      <table class="table is-size-5" id="table">
          <thead>
              <tr>
                  <th scope="col">#</th>
                  <th scope="col">Comida</th>
                  <th scope="col">Cantidad</th>
                  <th scope="col">Acción</th>
                  <th scope="col">Total</th>
              </tr>
          </thead>
          <tbody>
              <Item
              v-for="item in items" :key="item.id"
              :item="item"
                />
          </tbody>
          <tfoot>
              <tr>
                  <th scope="row" colspan="5" v-if="Object.keys(items).length === 0">¡En sus marcas, listos a comprar!</th>
                  <Footer v-else />
              </tr>
          </tfoot>
      </table>
  </div>
</template>

<script>
import { computed } from '@vue/reactivity'
import {useStore} from 'vuex'
import Item from './Item'
import Footer from './Footer'
export default {
    components:{
        Item,
        Footer
    },
    setup(){
        const store = useStore()
        const items = computed(()=> store.state.carrito)

        return{items}
    }
}
</script>

<style scope>
    .table-container{
        text-align: center;  
        background-color: var(--sand); 
        padding-bottom: 55px;   
        height: auto;       
    }
    .title-container{
        padding-bottom: 10px;
        padding-top: 10px;
    }
    .table-container h2{
        color: var(--orange);
        font-size: 35px;
        font-weight: 500;
    }
    table{
        margin: auto;  
        width: 60%;
        border-radius: 8px;
    }
    #table{
       background-color: var(--ocher);
       border-radius: 5px;
       color: var(--dark-grey); 
    }
</style>