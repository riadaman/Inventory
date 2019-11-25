<template>
  <div id="app">
  <navbar></navbar>
<div class="container">
<div class="row">
  <div class="col-sm-9">
   <inventory></inventory>
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

export default {
 components:{
   Navbar,Cart,Inventory
 }
}
</script>

<style>
 .container {
   margin-top: 50px;
 }
</style>
