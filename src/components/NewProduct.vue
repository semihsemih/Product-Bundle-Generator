<template>
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
</template>

<script>
  import DefaultProductPhoto from '../assets/images/default-photo.png';

  export default {
    name: "NewProduct",
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

<style scoped>
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
</style>