<template>
  <div class="grid container">
    <div class="sub_category_page">
      <div class="column_right column_right_products_container">
        <div class="product__area">
          <!--TEMPLATE-->
          <div id="products_section">
            <div class="products_page pg_0">
              <div class="product product_horizontal">
                <span class="product_code"
                  >Код: {{ parseInt(product.code, 10) }}
                </span>
                <div class="product_status_tooltip_container">
                  <span class="product_status">Наличие</span>
                </div>
                <div class="product_photo">
                  <a href="#" class="url--link product__link">
                    <img :src="imgSourse" />
                
                  </a>
                </div>
                <div class="product_description">
                  <a href="#" class="product__link">{{ product.title }}</a>
                </div>
                <div class="product_tags hidden-sm">
                  <p>Могут понадобиться:</p>
                  <a
                    href="#"
                    class="url--link"
                    v-for="(assocProduct, i) of assocProducts"
                    v-bind:assocProducts="assocProducts"
                    v-bind:key="i"
                  >
                    {{ assocProduct }}</a
                  >
                </div>
                <ProductPrice v-bind:product="product" />
                <div class="product_price_points">
                  <p class="ng-binding">
                    Можно купить за {{ (Math.random() * 500).toFixed(2) }} балла
                  </p>
                </div>
                <div class="list--unit-padd"></div>
                <div class="list--unit-desc">
                  <div class="unit--info">
                    <div class="unit--desc-i" :style="{ marginRight: '20px' }">
                      <svg>
                        <use xlink:href="@/assets/images/sprite.svg#info"></use>
                      </svg>
                    </div>
                    <div class="unit--desc-t">
                      <p>
                        <span class="ng-binding">Продается упаковками:</span>
                        <span class="unit--infoInn"
                          >1 упак. = {{ (Math.random() * 5).toFixed(2) }} м. кв.
                        </span>
                      </p>
                    </div>
                  </div>
                </div>
                <ProductCounter v-bind:product="product" />
              </div>
            </div>
          </div>
          <!--TEMPLATE-->
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import ProductPrice from "@/components/ProductPrice";
import ProductCounter from "@/components/ProductCounter";

export default {
  name: "Product",
  components: {
    ProductPrice,
    ProductCounter,
  },
  props: {
    product: Object,
  },
  data() {
    return {
      imgName: "df126-52f2-11e5-b9a9-00259036a192",
    };
  },
  computed: {
    assocProducts: function () {
      let assocProducts = this.product.assocProducts
        .replace(/\n/g, "")
        .replace(/;$/, "")
        .replace(/;/g, ",;");
      return assocProducts.split(";");
    },
    imgSourse: function() {
      return require(`../assets/images/${this.imgName}_220x220_1.jpg`);
    },
  },
};
</script>

<style scoped>
.product .product_unit__desc .unit--desc-i {
  margin: 5px 25px 00;
}
</style>

