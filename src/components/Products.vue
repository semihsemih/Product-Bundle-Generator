<template>
  <div class="col-md-4 pl-5 product-card-container">
    <div class="mb-3"></div>
    <Product>

      <div class="row no-gutters">
        <div class="col-md-4">
          <img src="../assets/images/demo2.png" class="card-img" alt="product-title">
        </div>
        <div class="col-md-8">
          <div class="card-body">
            <span class="card-text"><b>Product Name: </b>Liquid Soap</span><br>
            <span class="card-text"><b>Piece: </b>3</span><br>
            <span class="card-text"><b>Unit Price: </b>24 $</span><br>
            <span class="card-text"><b>Total Price: </b>72 $</span>
          </div>
        </div>
      </div>
    </Product>
    <div class="mt-3"></div>
  </div>
</template>

<script>
  import Product from "./Product";

  export default {
    name: "Products",
    components: {
      Product
    }
  }
</script>

<style scoped>
  .product-card-container {
    overflow-y: scroll;
    max-height: 680px
  }

  .product-card {
    max-width: 540px;
  }
</style>