<template>
  <div>
    <div class="product_units">
      <div class="unit--wrapper">
      <form> 
          <div class="unit--select" @click="toggleMeter" :class="{'unit--active': meterActive}">
            <p class="ng-binding">За м.кв.</p>
          </div>
          <div class="unit--select" @click="togglePack" :class="{'unit--active': packActive}">
            <p class="ng-binding">За упаковку</p>
          </div>

        </form> 
      </div>
    </div>
    <p class="product_price_club_card">
      <span :style="{ marginRight: '10px' }" class="product_price_club_card_text">По карте<br />клуба</span>
      <span class="goldPrice" v-if="meterActive">{{Math.trunc(product.priceGoldAlt)}}</span>
      <span class="goldPrice" v-if="packActive">{{Math.trunc(product.priceGold)}}</span>
      <span class="rouble__i black__i">
        <svg
          version="1.0"
          id="rouble__b"
          xmlns="http://www.w3.org/2000/svg"
          x="0"
          y="0"
          width="30px"
          height="22px"
          viewBox="0 0 50 50"
          enable-background="new 0 0 50 50"
          xml:space="preserve"
        >
          <use
            xmlns:xlink="http://www.w3.org/1999/xlink"
            xlink:href="@/assets/images/sprite.svg#rouble_black"
          ></use>
        </svg>
      </span>
    </p>
    <p class="product_price_default">
      <span class="retailPrice" v-if="meterActive">{{Math.trunc(product.priceRetailAlt)}}</span>
      <span class="retailPrice" v-if="packActive">{{Math.trunc(product.priceRetail)}}</span>
      <span class="rouble__i black__i">
        <svg
          version="1.0"
          id="rouble__g"
          xmlns="http://www.w3.org/2000/svg"
          x="0"
          y="0"
          width="30px"
          height="22px"
          viewBox="0 0 50 50"
          enable-background="new 0 0 50 50"
          xml:space="preserve"
        >
          <use
            xmlns:xlink="http://www.w3.org/1999/xlink"
            xlink:href="@/assets/images/sprite.svg#rouble_gray"
          ></use>
        </svg>
      </span>
    </p>

  </div>
</template>

<script>
export default {
  name: "ProductPrice",
  props: {
    product: Object,
  },
  data() {
    return {
      meterActive: true,
      packActive: false,
    };
  },
  methods: {
    toggleMeter() {
      this.meterActive = true;
      this.packActive = false
    },
    togglePack() {
      this.meterActive = false;
      this.packActive = true
    },
  }

};
</script> 