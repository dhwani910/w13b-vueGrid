<template>
  <div id="app">
    <!-- <h3>{{ switchState }}</h3> -->
    <vue-tweets :tweets="tweetList"></vue-tweets>
    
    <vue-container></vue-container>
    <vue-to-do></vue-to-do>
    
  </div>
</template>

<script>

import VueTweets from './components/Tweets.vue'
import VueContainer from './components/TweetContainer.vue'
import VueToDo from './components/ToDo.vue'
export default {
  name: 'App',
  components: {
    VueTweets,
    VueContainer,
    VueToDo,
    
  },
  data(){
    return{
      // switchState: true
        tweetList: [
                {
                    author: 'dhwani',
                    date: 'December 12,2020',
                    text: 'hello world i am a tweet!!!'
                },
                {
                    author: 'karen',
                    date: 'December 11,2020',
                    text: 'you can ask me anytime'
                },
                {
                    author: 'nikki',
                    date: 'December 14,2020',
                    text: 'having fun'
                },
            ]

    }
  },
  // methods: {
  //   callback(value){
  //     this.switchState = value
  //   }
    
  // }
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
