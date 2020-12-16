<template>
<div>
     <button class="button is-info" @click="toggleview">Toggle View</button>
    <div id="tweets" :class="{ 'list-view': listView}">

   
        <article class="tweet " v-for="(tweet, index) in tweets"  :key="index">
            <h4>{{tweet.author}}</h4>
             <h6>{{tweet.date}}</h6>
             <p>{{tweet.text}}</p>

        </article>
        
        

    </div>
    
</div>
    
</template>





<script>
export default {
    name: 'vue-tweets',
    data(){
        return{
            listView: true,
            tweets: [
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

    methods: {
        toggleview(){
            this.listView = !this.listView;
            // this.$emit('click', this.listView)
            if(this.listView == true){
                document.querySelector('button').innerText = "List View";
            }else{
                document.querySelector('button').innerText = "Grid View";
            }
        }
    }
    
}

</script>





<style scoped>

#tweets{
    display: grid;
    grid-template-columns: repeat(2, 1fr);
    grid-gap: 1rem;
    padding: 1rem;
}

#tweets.list-view{
    grid-template-columns: 1fr;
}
article{
    padding: 1rem;
    margin: 1rem;
    background-color: rgb(211, 185, 240);


}
@media only screen and (min-width: 991px){
    #tweets{
        display: grid;
        grid-template-columns: repeat(3, 1fr);
    
    }
    
}

</style>