<template>
  <div class="fond" style="padding-top: 50px">
        <div v-for="element in results" :key="element.id" >
            <br>
            <br>
            <span class="boldRed"></span><span class="text">{{ element.id }}</span>
            <br>
            <br>
            <span class="boldRed">{{ element.setup }}</span>
            <br>
            <br>
            <span class="boldRed">{{ element.punchline }}</span>
            <br>
            <br>
        </div>
    </div>
</template>

<script>
import axios from 'axios';
    export default {
        name: "Joke",
        data(){
            return{
                results: []
            }
        },
        methods: {
            getMyJoke(){
                axios.get('https://official-joke-api.appspot.com/jokes/programming/ten')
                .then((joke) => {
                    console.log(joke.request.response);
                    this.results = JSON.parse(joke.request.response)
                })
                .catch(() => {
                    this.results = "PAS DE JOKE JE SUIS LA TRISTESSE";
                })
            }
        },
        mounted: function () {
            this.getMyJoke()
        }
    }

</script>

<style>
    .fond{
        background-color: white;
        color: black;
        background-repeat: no-repeat;
        text-align: center;
        
        
    }
    .collapsible {
    background-color: #777;
    color: white;
    cursor: pointer;
    padding: 18px;
    width: 100%;
    border: none;
    text-align: left;
    outline: none;
    font-size: 15px;
}

.active, .collapsible:hover {
    background-color: #555;
}

.content {
    padding: 0 18px;
    display: none;
    overflow: hidden;
    background-color: #f1f1f1;
}
</style>