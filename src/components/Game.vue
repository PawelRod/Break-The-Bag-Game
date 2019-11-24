<template>
  <div class="game">
    <!-- bag image -->
    <div id="bag" v-bind:class="{burst: ended}">
    
    </div>

    <!-- bag health -->
    <div class="condition__block">
      <h3>BAG CONDITION:</h3>
      <div id="bag-health">
        <div v-bind:style="{width: health + '%'}"></div>
      </div>
    </div>

    <!-- game controls -->
    <div id="controls">
      <button @click="punch" v-show="!ended">PUNCH</button>
      <button @click="restart">RESTART</button>
    </div>
  </div>
</template>

<script>
export default {
  name: 'Game',
  data() {
    return {
      health: 100,
      ended: false,
    }
  },
  methods: {
    punch: function() {
      this.health -= 10;
      if (this.health <= 0) {
        this.ended = true;
      }
    },
    restart: function() {
      this.health = 100;
      this.ended = false;
    }
  },
  computed: {

  },
}
</script>

<style scoped>
  @import url('https://fonts.googleapis.com/css?family=Alata&display=swap');

  .game {
    font-family: 'Alata', sans-serif;
    text-align: center;
    letter-spacing: 1px;
    height: 100%;
    width: 100%;
  }
  #bag {
    width: 200px;
    height: 450px;
    margin: 0 auto;
    background: url(/assets/bag.png) center no-repeat;
    background-size: 80%;
  }
  #bag.burst {
    background: url(/assets/bag-burst.png) center no-repeat;
    background-size: 80%;
  }
  .condition__block {
    border: 2px solid black;
        border-radius: 10px;
    width: 300px;
    background: #a5a3a3;
    margin: 10px auto;
  }
  #bag-health {
    width: 200px;
    border: 3px solid black;
    margin: 20px auto;
    background: black;
  }
  #bag-health div {
      height: 20px;
      background: crimson;
  }
  #controls {
    border: 2px solid black;
    border-radius: 10px;
    width: 300px;
    background: #a5a3a3;
    margin: 15px auto;
    padding: 20px 0;
  }
  #controls button {
    margin: 0 15px;
    background: crimson;
    color: black;
    font-weight: bold;
    font-size: 16px;
    border: 2px solid black;
    border-radius: 20px;
    padding: 10px 20px;
  }
  #controls button:active {
    padding: 8px 16px;
  }
</style>
