<template>
  <div id="app">
    <Game />
  </div>
</template>

<script>
import Game from './components/Game.vue'

export default {
  name: 'app',
  components: {
    Game
  }
}
</script>

<style>
  html, body, #app {
    height: 100%;
    min-height: 100%;
    width: 100%;
    padding: 0;
    margin: 0;
    background: #7e7e7e;
    box-shadow: inset 0px 0px 106px 9px rgba(0,0,0,1);
  }
</style>
