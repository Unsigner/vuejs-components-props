<template>
<div>
  <my-header></my-header>
  <div class="container">    
      <products @viewDetails="viewDetails"></products>
      <product-details :product="selectedProduct"></product-details>
  </div>
</div>
</template>

<script>
import ProductsList from './ProductsList.vue'
import ProductDetails from './ProductDetails.vue'
import myHeader from './Header.vue'

export default {
  data(){
    return {
      selectedProduct: {}
    }
  },
  components: {
    myHeader,
    'products': ProductsList,
    ProductDetails,
  },  
  methods:{
    viewDetails(product){
      this.selectedProduct = product;
    }
  }
}
</script>

<style>
  .container{
    display:flex;
    align-items:flex-start;
  }
</style>
