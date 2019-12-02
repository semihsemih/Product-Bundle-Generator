<template>
  <div id="container">
    <h1 class="text-center mt-5 mb-5">Product Bundle Generator</h1>
    <div class="row justify-content-between">
      <div class="col-md-6 divider d-flex justify-content-center">
        <NewProduct/>
      </div>
      <Products/>
      <div class="col-md-2"></div>
      <div class="col-md-8 mt-5 mx-auto">
        <Progress/>
      </div>
    </div>
  </div>
</template>

<script>
  import NewProduct from "./components/NewProduct";
  import Progress from "./components/Progress";
  import Products from "./components/Products";
  export default {
    name: 'app',
    components: {
      NewProduct,
      Progress,
      Products
    }
  }
</script>

<style>
  .divider {
    border-right: 1px solid black
  }
</style>
