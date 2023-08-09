<template>
  <div class="v-cart-item">
    <img class="v-cart-item__image" :src="require('../assets/images/' + cart_item_data.image)" alt="pic">
		<!-- <p class="v-catalog-item__image">{{product_data.image}}</p> -->
		<!-- <p class="v-catalog-item__name">{{ product_data.name }}</p>
		<p class="v-catalog-item__price">{{ product_data.price }}</p>
		<p class="v-catalog-item__price">{{ product_data.about }}</p> -->
    <div>
      <p class="v-catalog-item__name">{{ cart_item_data.name }}</p>
      <p class="v-catalog-item__price">{{ cart_item_data.price }}</p>
      <p class="v-catalog-item__price">{{ cart_item_data.article }}</p>
      <p class="v-catalog-item__price">{{ cart_item_data.about }}</p>
    </div>
    <div class="v-cart-item__quantity">
      <p>quantity</p>
      <span>
        {{ cart_item_data.quantity }}
      </span>
      
    </div>
    <button @click="deleteFromCart">Delete</button>
  </div>
</template>
  
  <script>
    export default {
      name: "v-cart-item",
      props: {
        cart_item_data:{
          type: Object,
          default(){
            return {};
          }
        }
      },
      data() {
        return {};
      },
      computed:{},
      methods:{
        deleteFromCart(){
          this.$emit('deleteFromCart')
        },
      },
      watch:{},
      mounted(){
        console.log('hello');
      }
    };
</script>
  
<style lang="scss">
.v-cart-item{
	display: flex;
	justify-content: space-between;
  flex-wrap: wrap;
	align-items: center;
  flex-basis: 33.33%;
	// max-width: 900px;
	// margin: 0 auto;
  box-shadow: 0 0 8px grey;
  padding: 20px;
  // margin: 15px;
  &__image{
    max-width: 100%;
  }
}
</style>