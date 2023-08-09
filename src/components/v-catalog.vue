<template>
  <h1>hello i'm catalog</h1>
  <div class="v-catalog">
    
    <vCatalogItem 
        v-for="product in PRODUCTS" :key="product.article"
        :product_data="product"
        @hello="showArticleFromChild"
    />
  </div>
</template>

<script>
import vCatalogItem from './v-catalog-item.vue';
import {mapActions, mapGetters} from 'vuex';
export default {
  name: "v-catalog",
  props: {},
  components: { vCatalogItem },
  data() {
    return {
      
    }
  },
  computed:{
    ...mapGetters(['PRODUCTS']),
  },
  methods:{
    ...mapActions([
    "GET_PRODUCTS_FROM_API"
    ]),
    showArticleFromChild(data){
      console.log(data);
    },
   
  },
  mounted(){
      this.GET_PRODUCTS_FROM_API()
      .then((responce)=>{
        if(responce.data){
          console.log('data is come');
        }
      })
    }
};
</script>

<style lang="scss">
.v-catalog{
  display: flex;
  justify-content: space-between;
  flex-wrap: wrap;
  align-items: center;
}
</style>