<template>
  <div class="product__wrapper">
    <div class="product_count_wrapper">
      <div class="stepper">
        <input
          class="product__count stepper-input"
          type="number"
          min="1"
          max="100"
          v-model.number="productAmmount"
        />
        <button @click="toIncrease" class="stepper-arrow up"></button>
        <button @click="toDecrease" class="stepper-arrow down"></button>
      </div>
    </div>
    <BuyButton :product="product" :productAmmount="productAmmount" />
  </div>
</template>

<script>
import BuyButton from "@/components/BuyButton";
export default {
  name: "ProductCounter",
  components: {
    BuyButton,
  },
  props: {
    product: Object,
  },
  data() {
    return {
      productAmmount: 1,
    };
  },
  methods: {
    toIncrease() {
      this.productAmmount = this.productAmmount + 1;
    },
    toDecrease() {
      this.productAmmount = this.productAmmount - 1;
    },
  },
};
</script> 