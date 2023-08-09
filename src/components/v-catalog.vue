<template>
  <h1>hello i'm catalog</h1>
  <div class="v-catalog">
    <div class="v-catalog__list">
      <vCatalogItem v-for="product in PRODUCTS" :key="product.article" :product_data="product" @addToCatr="addToCatr" />
    </div>
  </div>
</template>

<script>
import vCatalogItem from './v-catalog-item.vue';
import { mapActions, mapGetters } from 'vuex';

export default {
  name: "v-catalog",
  props: {},
  components: { vCatalogItem },
  data() {
    return {

    }
  },
  computed: {
    ...mapGetters(['PRODUCTS']),
    // PRODUCTS(){
    //   return this.$store.getters.PRODUCTS;
    // }
  },
  methods: {
    ...mapActions([
      "GET_PRODUCTS_FROM_API", "ADD_TO_CART"
    ]),
    addToCatr(data) {
      console.log(data);
      this.ADD_TO_CART(data)
    },

  },
  mounted() {
    this.GET_PRODUCTS_FROM_API()
      .then((responce) => {
        if (responce.data) {
          console.log('data is come');
        }
      })
  }
};
</script>

<style lang="scss">
.v-catalog, .v-catalog__list {
  display: flex;
  justify-content: space-between;
  flex-wrap: wrap;
  align-items: center;
  margin-bottom: 25px;
  &__list{
    
  }
}
</style>