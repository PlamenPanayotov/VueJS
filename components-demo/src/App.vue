<template>
  <div id="app">
    <img alt="Vue logo" src="./assets/logo.png">
    <HelloWorld msg="Welcome to Your Vue.js App"/>
    <ProductList :products="products" />
    <!-- <Counter v-bind:counter="counter" />
    <Counter v-bind:counter="counter" />
    <Counter v-bind:counter="counter" /> -->
  </div>
</template>

<script>
import HelloWorld from './components/HelloWorld.vue'
import ProductList from './components/ProductList.vue'


export default {
  name: 'App',
  data: function () {
    return {
      counter: 0,
      products: [
        { 
          type: 'Spaghetti', 
          price: 11, 
          ingredients: [ 'Pasta', 'Meatballs', 'Sause' ]
        },
        { 
          type: 'Musaka', 
          price: 5, 
          ingredients: [ 'Potatoes', 'Mince', 'Eggs' ]
        },
        { 
          type: 'Pancakes', 
          price: 11, 
          ingredients: [ 'Eggs', 'Flour', 'Milk' ]
        }
      ]
    }
  },
  components: {
    HelloWorld,
    ProductList
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
