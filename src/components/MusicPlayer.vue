<template>
  <div class="multimedia-frame">
    <div class="image-container">
        <div class="img-icons">
            <i class="player-arrows fas fa-exchange-alt"></i>
            <i class="player-arrows fas fa-random"></i>              
            <i class="player-arrows fas fa-redo-alt"></i>
        </div>
        <div class="img-nav">
            <i class="player-navigation fas fa-bars" @click="test()"></i>
        </div>
        <div class="img-foot">
            <p class="song-artist">Icona Pop</p>
            <p class="song-title">Still Don't Know</p>
        </div>
        <img src="https://cdns-images.dzcdn.net/images/artist/2b1eabd727330318a4507c295897887f/500x500.jpg">
    </div>
    <div id=timing-belt>
        <div class="time-passed" :style="{width: time + '%'}"></div>
        <input id="slider" type="range" min="0" max="100" v-model='time'>
    </div>
    <div class="buttons-container">
        <div class="share-btn"><i class="player-btn-side-icons fas fa-share-alt"></i></div>
        <div class="player-btn"><i class="player-btn-icons fas fa-step-backward"></i></div>
        <div class="player-btn-lg"><i class="player-btn-pause far fa-pause-circle"></i></div>
        <div class="player-btn"><i class="player-btn-icons fas fa-step-forward"></i></div>
        <div class="fav-btn"><i class="player-btn-side-icons fas fa-heart"></i></div>
    </div>
  </div>
</template>


<script>
export default {
  name: 'HelloWorld',
  props: {
    msg: String
  },
  data () {
    return {
        time: 60,
    }
  },
  methods: {
    test(){
        console.log('test')
    }
  }
}
</script>

<style scoped>

/* media frame */

.multimedia-frame {
    margin: 2rem 1rem;
    background-color: rgb(243, 232, 241);
    height: 80vh;
    border-radius: 2rem;
    -webkit-box-shadow: 0px 14px 22px 4px rgba(106, 2, 125, 0.8);
    -moz-box-shadow: 0px 14px 22px 4px rgba(106, 2, 125, 0.8);
    box-shadow: 0px 14px 22px 4px rgba(106, 2, 125, 0.8);
}
.image-container {
    position: relative;
    overflow: hidden;
    object-fit: cover;
    border-radius: 2rem 2rem 0 0;
    height: 55vh;
}
.image-container img {
    width: 100%;
    height: 100%;
    object-fit: cover;
}
.image-container .img-icons {
    display: flex;
    flex-direction: row;
    align-items: stretch;
    justify-content: center;
    text-align: center;
    position: absolute;
    width: 100%;
    height: 20%;
    background: linear-gradient(90deg, rgba(36,0,38,0.7371323529411764) 0%, rgba(0,0,0,0.3309698879551821) 50%, rgba(45,0,48,0.6923144257703081) 100%);
}
.img-icons .player-arrows {
    display: flex;
    align-items: center;
    font-size: 1.2rem;
    margin: 1rem;
    color: white;
}
.image-container .img-nav {
    display: flex;
    flex-direction: row;
    align-items: stretch;
    justify-content: center;
    position: absolute; 
    width: 100%;
    height: 20%;
}
.img-nav .player-navigation {
    display: flex;
    align-items: center;
    right: 0;
    font-size: 1.2rem;
    justify-content: flex-end;
    margin: 1rem;
    width: 100%;
    color: rgba(255, 255, 255, 0.49);
}

.image-container .img-foot {
    display: flex;
    flex-direction: column;
    align-items: stretch;
    justify-content: center;
    text-align: center;
    position: absolute;
    bottom: 0;
    width: 100%;
    height: 20%;
    background: linear-gradient(90deg, rgba(36,0,38,0.7371323529411764) 0%, rgba(0,0,0,0.3309698879551821) 50%, rgba(45,0,48,0.6923144257703081) 100%);
}
.img-foot p {
    color: white;
    margin: 0;
}
.song-artist {
    font-weight: 600;
    font-size: 1.4rem;
}
.song-title {
    font-size: 1.2rem;
}

/* time slider */

#timing-belt {
    position: relative;
    padding: 0;
    height: 1rem;
    background-color: rgb(218, 80, 72);
}
#slider {
    -webkit-appearance: none;
    position: absolute;
    margin: 0;
    width: 100%;
    height: 100%;
    outline: none;
    border-radius: 0;
    background-color: rgba(218, 79, 72, 0);
}
#slider::-webkit-slider-thumb {
    -webkit-appearance: none;
    display: flex;
    align-content: center;
    align-items: center;
    justify-content: center;
    border-radius: 50px;
    height: 1.2rem;
    width: 1.2rem;
    color: blueviolet;
    background-color: rgb(255, 255, 255);
    -webkit-box-shadow: 0px 1px 2px 1px rgba(106, 2, 125, 0.8);
    -moz-box-shadow: 0px 1px 2px 1px rgba(106, 2, 125, 0.8);
    box-shadow: 0px 1px 2px 1px rgba(106, 2, 125, 0.8);
    z-index: 3;
}
.time-passed {
    pointer-events: none;
    position: absolute;
    margin: 0;
    height: 100%;
    outline: none;
    border-radius: 0;
    background-color: rgb(255, 255, 255);
}

/* buttons */

.buttons-container {
    background-color: rgba(127, 255, 212, 0);
    position: relative;
    border-radius: 0 0 2rem 2rem;
    width: 100%;
    height: 28%;
    display: flex;
    flex-direction: row;
    flex-wrap: wrap;
    justify-content: center;
    align-items: center;
    align-content: center;
}
.player-btn {
    margin: 0;
    display: flex;
    align-items: center;
    color: white;
    background-color: rgb(55, 26, 123);
    border-radius: 2rem;
    height: 2rem;
    width: 2rem;
}
.player-btn-lg {
    margin: 1rem;
    display: flex;
    align-items: center;
    color: white;
    background-color: rgb(55, 26, 123);
    border-style: solid;
    border-width: 0.4rem;
    border-radius: 100%;
    height: 3rem;
    width: 3rem;
}
.player-btn-icons {
    position: absolute;
    font-size: 1rem;
    color: white;
    transform: translate(63%);
}
.player-btn-pause {
    position: absolute;
    font-size: 2rem;
    color: white;
    transform: translate(25%);
}
.share-btn {
    margin: 0;
    display: flex;
    align-items: center;
    color: rgb(55, 26, 123);
    background-color: rgb(255, 255, 255);
    border-radius: 2rem;
    height: 2rem;
    width: 2rem;
    margin-right: 1.5rem;
}
.fav-btn {
    margin: 0;
    display: flex;
    align-items: center;
    color: rgb(55, 26, 123);
    background-color: rgb(255, 255, 255);
    border-radius: 2rem;
    height: 2rem;
    width: 2rem;
    margin-left: 1.5rem;
}
.player-btn-side-icons {
    position: absolute;
    font-size: 1rem;
    transform: translate(50%);
}


</style>
