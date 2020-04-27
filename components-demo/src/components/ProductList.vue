<template>
  <div>
      <p>This is my product List</p>
      <Product v-for="(p, i) in products"
      :type="p.type"
      :price="p.price"
      :ingredients="p.ingredients"
      :key="i"  />
  </div>
</template>

<script>    
import Product from './Product.vue'
export default {
  name: 'ProductList',
    props: {
        products: Array
    },
  data: function () {
      return {
       
      }
  },
  components: {
      Product
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

</style>
