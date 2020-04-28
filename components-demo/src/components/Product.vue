<template>
  <div>
      <p>{{ mealType }}</p>
      <p>{{ price }}</p>
      <ul>
          <li v-for="(ing, i) in ingredients" :key="i">{{ing}}</li>
      </ul>
      <div>{{expirationDate}}</div>
  </div>
</template>

<script>    
export default {
  name: 'Product',
  props: {
            mealType: {
              type: String,
              required: true
            },
            price: Number,
            ingredients: Array,
            expirationDate: {
              type: Date,
              default: () => new Date()
            }
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
