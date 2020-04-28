<template>
  <div id="app">
    <button @click="selectedComponent = 'HelloWorld'">Render HelloWorld</button>
    <button @click="selectedComponent = 'ProductList'">Render ProductList</button>
    <component :is="selectedComponent" 
    msg="Welcome to Your Vue.js App"
    :products="products" 
    :title="title" 
    @onChangeTitle="title = $event"
    >
      
    </component>
    <!-- <HelloWorld msg="Welcome to Your Vue.js App"/>
    <ProductList 
    :products="products" 
    :title="title" 
    @onChangeTitle="title = $event" />  -->
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
          mealType: 'Spaghetti', 
          price: 11, 
          ingredients: [ 'Pasta', 'Meatballs', 'Sause' ]
        },
        { 
          mealType: 'Musaka', 
          price: 5, 
          ingredients: [ 'Potatoes', 'Mince', 'Eggs' ]
        },
        { 
          mealType: 'Pancakes', 
          price: 11, 
          ingredients: [ 'Eggs', 'Flour', 'Milk' ]
        }
      ],
      title: 'This is my product list!',
      selectedComponent: 'HelloWorld',
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
