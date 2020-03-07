<template>
  <div >
  
   购物车

  </div>
</template>

<script>
	export default {
		name: "Cart",
    components: {

    },
    computed: {
		  cartList() {
		    return this.$store.getters.cartList
      },
      cartCount() {
		    return this.$store.getters.cartCount
      }
    }
	}
</script>

<style scoped>

</style>
