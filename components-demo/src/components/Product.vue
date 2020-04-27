<template>
  <div>
      <p>{{ type }}</p>
      <p>{{ price }}</p>
      <ul>
          <li v-for="(ing, i) in ingredients" :key="i">{{ing}}</li>
        
      </ul>
  </div>
</template>

<script>    
export default {
  name: 'Product',
  props: {
            type: String,
            price: Number,
            ingredients: Array
        },
  data: function () {
      return {
        
      }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

</style>
