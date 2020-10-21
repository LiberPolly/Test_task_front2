<template>
  <div class="catalogue">
  <Product
    v-for="(product) of productList"
    v-bind:product="product"
    v-bind:key="product.productId"
  />
  </div>
</template>

<script>
import {products} from "@/components/products.js";
import Product from "@/components/Product";

export default {
  name: 'Catalogue',
  components: {
    Product,
  },
  data() {
    return {
      productList: products,
    };
  }, 
}
</script>


<style>

</style>
