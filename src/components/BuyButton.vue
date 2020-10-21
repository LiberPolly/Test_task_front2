<template>
  <button
    class="btn btn_cart"
    data-url="/cart/"
    :data-product-id="product.productId"
  >
    <svg class="ic ic_cart">
      <use
        xmlns:xlink="http://www.w3.org/1999/xlink"
        xlink:href="@/assets/images/sprite.svg#cart"
      ></use>
    </svg>

    <span class="ng-binding">В корзину</span>
  </button>
</template>

<script>
export default {
  name: "BuyButton",
  props: {
    product: Object,
    productAmmount: Number,
  },
};
</script>

<style lang="less" scoped>
.ic_cart {
  fill: white;
}
</style>