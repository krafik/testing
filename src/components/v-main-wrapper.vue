<template>
	<div class="v-main-wrapper">

		<vCart v-if="CART.length" :cart_data="CART" />
		<vCatalog />


	</div>
</template>

<script>
import vCatalog from './v-catalog.vue';

import vCart from './v-cart.vue';
import { mapGetters } from 'vuex';
export default {
	name: 'v-main-wrapper',
	components: { vCatalog, vCart },
	props: {},
	data() {
		return {
			title: 'hello folks'
		}
	},
	//вычисляемые свойства
	computed: {
		...mapGetters(['CART'])
	},
	methods: {},
	watch: {},
	mounted() {
		console.log('hello');
	}
}
</script>

<style lang="scss">
.v-main-wrapper {
	// display: flex;
	// justify-content: center;
	// align-items: center;
	// flex-direction: column;
	max-width: 900px;
	margin: 0 auto;
}
</style>