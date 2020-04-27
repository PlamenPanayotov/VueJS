<template>
  <div id="app">
    <div class="counter">
      <h1>
        60
      </h1>
    </div>
    <section class="memory-game">
      <div
        v-for="card in cards"
        class="memory-card"
        :class="{ flip: card.flipped }"
        data-framework="aurelia"
        :key="card.id"
        :data="cards"
        v-on:click="card.flipped = !card.flipped"
      ><p>{{card.id}}</p>
        <img class="front-face" :src="card.imgSrc" :imgAlt="card.imgAlt" />
        <img class="back-face" src="img/js-badge.svg" alt="JS Badge" />
        
      </div>
    </section>
  </div>
</template>

<script>
export default {
  name: 'app',
  data: function() {
    return {
      cards: [
        {
          id: 5,
          imgSrc: 'img/aurelia.svg',
          imgAlt: 'Aurelia',
          pair: 1,
          flipped: false,
        },
        {
          id: 2,
          imgSrc: 'img/aurelia.svg',
          imgAlt: 'Aurelia',
          pair: 1,
          flipped: false,
        },
        { id: 3, imgSrc: 'img/vue.svg', imgAlt: 'Vue', pair: 2, flipped: false },
        { id: 4, imgSrc: 'img/vue.svg', imgAlt: 'Vue', pair: 2, flipped: false },
        {
          id: 1,
          imgSrc: 'img/angular.svg',
          imgAlt: 'Angular',
          pair: 3,
          flipped: false,
        },
        {
          id: 6,
          imgSrc: 'img/angular.svg',
          imgAlt: 'Angular',
          pair: 3,
          flipped: false,
        },
        { id: 7, imgSrc: 'img/ember.svg', imgAlt: 'Ember', pair: 4, flipped: false },
        { id: 8, imgSrc: 'img/ember.svg', imgAlt: 'Ember', pair: 4, flipped: false },
        {
          id: 9,
          imgSrc: 'img/backbone.svg',
          imgAlt: 'Backbone',
          pair: 5,
          flipped: false,
        },
        {
          id: 10,
          imgSrc: 'img/backbone.svg',
          imgAlt: 'Backbone',
          pair: 5,
          flipped: false,
        },
        { id: 11, imgSrc: 'img/react.svg', imgAlt: 'React', pair: 6, flipped: false },
        { id: 12, imgSrc: 'img/react.svg', imgAlt: 'React', pair: 6, flipped: false },
      ],
    };
  },
   methods: {
     reverce: function () {
       this.cards.sort(() => Math.random() - 0.5);
       console.log(this.cards)
       return this.cards;
     }
   },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
#app {
  width: 100%;
  padding: 7%;
}
.memory-game {
  width: 640px;
  height: 640px;
  margin: auto;
  display: flex;
  flex-wrap: wrap;
  perspective: 1000px;
}

.memory-card {
  width: calc(25% - 10px);
  height: calc(33.333% - 10px);
  margin: 5px;
  position: relative;
  transform: scale(1);
  transform-style: preserve-3d;
  transition: transform 0.5s;
  box-shadow: 1px 1px 1px rgba(0, 0, 0, 0.3);
}

.disable-card {
  pointer-events: none;
}

.memory-card:active {
  transform: scale(0.97);
  transition: transform 0.2s;
}

.memory-card.flip {
  transform: rotateY(180deg);
}

.front-face,
.back-face {
  width: 100%;
  height: 100%;
  padding: 20px;
  position: absolute;
  border-radius: 5px;
  background: #fff29e;
  backface-visibility: hidden;
}

.front-face {
  transform: rotateY(180deg);
}

.counter {
  position: absolute;
  top: 0px;
  right: 0px;
}
</style>
