<template>
	<div class="v-catalog-item">
		<img class="v-catalog-item__image" :src="require('../assets/images/' + product_data.image)" alt="pic">
		<!-- <p class="v-catalog-item__image">{{product_data.image}}</p> -->
		<p class="v-catalog-item__name">{{ product_data.name }}</p>
		<p class="v-catalog-item__price">{{ product_data.price }}</p>
		<p class="v-catalog-item__price">{{ product_data.about }}</p>
		<button @click="addToCart" type="button" class="v-catalog-item__btn button">add to cart</button>
	</div>
</template>
  
<script>
export default {
	name: "v-catalog-item",
	props: {
		product_data: {
			type: Object,
			default() {
				return {};
			}
		}
	},
	data() {
		return {}
	},
	methods: {
		addToCart() {
			this.$emit('hello', this.product_data.article)
			this.$emit('addToCatr', this.product_data)
		}
	}
};
</script>
  
<style lang="scss">
.v-catalog-item {
	// display: flex;
	// flex-direction: column;
	// align-items: center;
	// flex-basis: 25%;
	// min-height: 329px;
	// box-shadow: 0 0 8px grey;
	// padding: 20px;
	// margin: 10px;

	// &__image {
	// 	max-width: 100%;
	// }
	flex-basis: 40%;
	box-shadow: 0 0 8px grey;
	padding: 20px;
	margin: 20px;
		&__image{
			width: 160px;
			display: block;
			margin: 0 auto;
		}
}
</style>