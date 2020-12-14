<template>
  <div id="app">
    <h3>{{ switchState }}</h3>
    <vue-tweets @click="callback"></vue-tweets>
    
    <vue-container></vue-container>
    
  </div>
</template>

<script>

import VueTweets from './components/Tweets.vue'
import VueContainer from './components/TweetContainer'
export default {
  name: 'App',
  components: {
    VueTweets,
    VueContainer,
    
  },
  data(){
    return{
      switchState: true
    }
  },
  methods: {
    callback(value){
      this.switchState = value
    }
    
  }
}
</script>

<style lang="scss">
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
