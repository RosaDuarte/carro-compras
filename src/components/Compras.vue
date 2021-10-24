<template>
  <div class="table-container">
      <div class="title-container block">
          <h4 class="title is-3">Carrito de compras</h4>
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
    }
    .title-container{
        background-color: rgba(58, 91, 109, .5);
        padding-bottom: 10px;
        padding-top: 10px;
    }
    .table-container h4{
        -webkit-text-fill-color: #d4ceb3;
        margin: auto;
        border-radius: 5px;
    }
    table{
        margin: auto;  
        font-family: Helvetica, sans-serif;
        width: 60%;
    }
    #table{
       background-color: rgba(255, 251, 244, .4);
       border-radius: 5px;
       color: #004b67;   
    }
</style>