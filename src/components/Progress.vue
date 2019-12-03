<template>
  <div class="progress" v-if="length > 0">
    <div class="progress-bar" role="progressbar" :style="'width: ' + length*10 + '%'" aria-valuenow="50" aria-valuemin="0"
         aria-valuemax="100">{{ length }} / 10
    </div>
  </div>
</template>

<script>
  import {eventBus} from "../main";

  export default {
    name: "Progress",
    data: function() {
      return {
        length: null
      }
    },
    created() {
      eventBus.$on('productListLength', (productListLength) => {
        this.length = productListLength;
      })
    }
  }
</script>

<style scoped>

</style>