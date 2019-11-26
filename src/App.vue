<template>
  <div id="app">
  <navbar @search="search" :items = "items"></navbar>
<div class="container">
<div class="row">
  <div class="col-sm-9">
   <inventory @newItemAdded="addCartItem" :items="items"></inventory>
  </div>
  <div class="col-sm-3">
    <cart @itemRemove="removeItem" :items="cart"></cart>
  </div>
</div>
  </div>
  </div>
</template>

<script>
import Navbar from '../src/components/Navbar'
import Inventory from '../src/components/Inventory'
import Cart from '../src/components/Cart'
import data from './data.js'

export default {
 components:{
   Navbar,
   Cart,
   Inventory
 },
 data(){
   return {
       items: [],
       cart: []
   }
 },
 mounted(){
   this.items = data
   //console.log(data)
 },
 methods: {
   search(keyword){
     this.items = data.filter(item =>{
       return item.title.toLocaleLowerCase().indexOf(keyword.toLocaleLowerCase())  !== -1
     })
   },
   addCartItem(item){
     this.cart.push(item)
   },
   removeItem(index){
     this.cart.splice(index,1)
   }
 }
}
</script>

<style>
 .container {
   margin-top: 50px;
 }
</style>
