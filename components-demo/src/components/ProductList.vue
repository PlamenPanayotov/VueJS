<template>
  <div>
      <p>{{title}}</p>
      <input type="text" :value="title" @input="changeTitle" />
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
        products: Array,
        title: String
    },
  data: function () {
      return {
       
      }
  },
  methods: {
    changeTitle(e) {
      const value = e.target.value
      this.$emit('onChangeTitle', value)
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
