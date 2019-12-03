<template>
  <div class="col-md-4 pl-5 product-card-container">
    <div class="mb-3"></div>
    <h4  v-if="productList.length === 0">Please add product.</h4>
    <Product v-for="product in productList" v-bind:key="product.id">
      <div v-if="productList.length > 0"  class="row no-gutters">
        <div class="col-md-4">
          <img :src="product.selectedImage" class="card-img" :alt="product.name">
        </div>
        <div class="col-md-8">
          <div class="card-body">
            <span class="card-text"><b>Product Name: </b>{{ product.name }}</span><br>
            <span class="card-text"><b>Piece: </b>{{ product.quantity }}</span><br>
            <span class="card-text"><b>Unit Price: </b>{{ product.price }} $</span><br>
            <span class="card-text"><b>Total Price: </b>{{ product.totalPrice }} $</span>
          </div>
        </div>
      </div>
    </Product>
    <div class="mt-3"></div>
  </div>
</template>

<script>
  import {eventBus} from "../main";
  import Product from "./Product";

  export default {
    name: "Products",
    data: function () {
      return {
        productList: []
      }
    },
    components: {
      Product
    },
    created() {
      eventBus.$on('newProduct', (product) => {
        if (this.productList.length < 10) {
          this.productList.push(product);
          eventBus.$emit('productListLength', this.productList.length)
        } else {
          alert('You can add up to 10 products.');
        }
      })
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