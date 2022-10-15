<template>
  <!-- eslint-disable -->
  <MusicPlayer/>
</template>

<script>
import MusicPlayer from './components/MusicPlayer.vue'

export default {
  name: 'App',
  components: {
    MusicPlayer
  }
}
</script>

<style>
body{
  background: linear-gradient(38deg, rgb(123, 120, 190) 0%, rgba(198,109,213,1) 35%, rgb(144, 66, 195) 100%) no-repeat center center fixed;
}
#app {
  font-size: 10px;
  font-family: 'Open Sans', sans-serif;
}

</style>
