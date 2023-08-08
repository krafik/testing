<template>
  <div class="v-cart-item">
    <img class="v-cart-item__image"  src="" alt="">
  </div>
</template>
  
  <script>
    export default {
      name: "v-cart-item",
      props: {},
      data() {
        return {};
      },
    };
</script>
  
<style lang="scss">
.v-cart-item{
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
}
</style>