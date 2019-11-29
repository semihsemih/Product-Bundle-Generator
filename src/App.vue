<template>
  <div id="container">
    <h1 class="text-center mt-5 mb-5">Product Bundle Generator</h1>
    <div class="row justify-content-between">
      <div class="col-md-6 divider d-flex justify-content-center">
        <div class="card product-uploader-card">
          <img class="product-uploader-photo" :src="selectedImage === null ? DefaultProductPhoto : selectedImage"
               alt="default-photo">
          <input ref="file" type="file" style="display: none;" @change="onChange($event)" class="form-control"/>
          <button class="btn btn-outline-secondary " type="button" @click="$refs.file.click()">
            Product Image Upload
          </button>
          <input type="text" class="form-control" placeholder="Product Name">
          <div class="d-flex justify-content-between">
            <div class="input-group">
              <input type="number" class="form-control number-input" placeholder="Quantity"
                     aria-label="Piece" aria-describedby="product-quantity">
            </div>
            <div class="input-group-append">
              <span class="input-group-text" id="product-quantity">Piece</span>
            </div>
            <div class="input-group">
              <input type="number" class="form-control number-input" placeholder="Price"
                     aria-label="Euro" aria-describedby="product-price">
              <div class="input-group-append">
                <span class="input-group-text" id="product-price">Euro</span>
              </div>
            </div>
          </div>
          <button class="btn btn-outline-secondary mt-4" type="button">
            Add Product
          </button>
        </div>
      </div>
      <div class="col-md-4 pl-5 product-card-container">
        <div class="mb-3"></div>
        <div class="card mb-3 product-card">
          <div class="row no-gutters">
            <div class="col-md-4">
              <img src="./assets/images/demo2.png" class="card-img" alt="product-title">
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
        </div>
        <div class="card mb-3 product-card">
          <div class="row no-gutters">
            <div class="col-md-4">
              <img src="./assets/images/demo2.png" class="card-img" alt="product-title">
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
        </div>
        <div class="card mb-3 product-card">
          <div class="row no-gutters">
            <div class="col-md-4">
              <img src="./assets/images/demo2.png" class="card-img" alt="product-title">
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
        </div>
        <div class="card mb-3 product-card">
          <div class="row no-gutters">
            <div class="col-md-4">
              <img src="./assets/images/demo2.png" class="card-img" alt="product-title">
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
        </div>
        <div class="card mb-3 product-card">
          <div class="row no-gutters">
            <div class="col-md-4">
              <img src="./assets/images/demo2.png" class="card-img" alt="product-title">
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
        </div>
        <div class="mt-3"></div>
      </div>
      <div class="col-md-2"></div>
      <div class="col-md-8 mt-5 mx-auto">
        <div class="progress">
          <div class="progress-bar" role="progressbar" style="width: 50%;" aria-valuenow="50" aria-valuemin="0" aria-valuemax="100">5 / 10</div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>

  import DefaultProductPhoto from './assets/images/default-photo.png';

  export default {
    name: 'app',
    data: function () {
      return {
        DefaultProductPhoto,
        selectedImage: null
      }
    },
    methods: {
      onChange(e) {
        const file = e.target.files[0];
        this.selectedImage = URL.createObjectURL(file);
      }
    }
  }
</script>

<style>
  .divider {
    border-right: 1px solid black
  }

  .product-uploader-card {
    width: 50%;
  }

  .product-uploader-photo {
    width: 100%;
  }

  .number-input {
    width: 50%;
    float: left
  }

  .product-card-container {
    overflow-y: scroll; max-height: 680px
  }

  .product-card {
    max-width: 540px;
  }
</style>
