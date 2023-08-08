<template>
	<div class="v-catalog-item">
		<img class="v-catalog-item__image" :src="require('../assets/images/' + product_data.image)" alt="pic">
		<!-- <p class="v-catalog-item__image">{{product_data.image}}</p> -->
		<p class="v-catalog-item__name">{{product_data.name}}</p>
		<p class="v-catalog-item__price">{{product_data.price}}</p>
		<p class="v-catalog-item__price">{{product_data.about}}</p>
		<button @click="sendDataToPerant"  type="button" class="v-catalog-item__btn button">add to cart</button>
	</div>
  </template>
  
  <script>
  export default {
	name: "v-catalog-item",
	props:{
		product_data:{
			type: Object,
			default(){
				return {};
			}
		}
	},
	data(){
	  return {}
	},
	methods:{
		sendDataToPerant(){
				this.$emit('hello', this.product_data.article)
		}
	}
  };
  </script>
  
  <style lang="scss">
  .v-catalog-item{
	display: flex;
	justify-content: space-between;
  flex-wrap: wrap;
	align-items: center;
  flex-basis: 25%;
	// max-width: 900px;
	// margin: 0 auto;
  box-shadow: 0 0 8px grey;
  padding: 20px;
  margin: 20px;
  &__img{
	max-width: 100%;
  }
}
  </style>