<template>
  <div id="app">
  <navbar :items = "items"></navbar>
<div class="container">
<div class="row">
  <div class="col-sm-9">
   <inventory :items="items"></inventory>
  </div>
  <div class="col-sm-3">
    <cart></cart>
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
       items: []
   }
 },
 mounted(){
   this.items = data
   //console.log(data)
 }
}
</script>

<style>
 .container {
   margin-top: 50px;
 }
</style>
