<template>
  <div class="v-main-wrapper">
<span></span>
	<vCatalog />
	
	<vCart />
  </div>
</template>

<script>
import vCatalog from './v-catalog.vue';

import vCart from './v-cart.vue';

export default {
	name: 'v-main-wrapper',
	components:{vCatalog,vCart},
	props:{},
	data(){
		return {
			title: 'hello folks'
		}
	},
	//вычисляемые свойства
	computed:{},
	methods:{},
	watch:{},
	mounted(){
		console.log('hello');
	}
}
</script>

<style lang="scss">
.v-main-wrapper{
	display: flex;
	justify-content: center;
	align-items: center;
	max-width: 900px;
	margin: 0 auto;
}
</style>