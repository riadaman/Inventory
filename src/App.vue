<template>
  <div id="app">
  <navbar :items = "items"></navbar>
<div class="container">
<div class="row">
  <div class="col-sm-9">
   <inventory @newItemAdded="addCartItem" :items="items"></inventory>
  </div>
  <div class="col-sm-3">
    <cart :items="cart"></cart>
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
       cart: [{
         id:1,
         title:'test',
         photo: "http://dummyimage.com/250x250.png/dddddd/000000",
         price: 100
       }]
   }
 },
 mounted(){
   this.items = data
   //console.log(data)
 },
 methods: {
   addCartItem(item){
     this.cart.push(item)
   }
 }
}
</script>

<style>
 .container {
   margin-top: 50px;
 }
</style>
