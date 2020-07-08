<template>
  <div id="contanier">
    <div class="row">
      <div class="col-md-8 offset-md-2 text-center">
          <h3 class="mt-5">English Dictionary</h3>
          <hr>
          <div class="words-contanier">
           <Word v-for="word in wordList" :word="word" :key="word.id"/>
          </div>
          <hr>
      </div>
    </div>
  </div>
</template>

<script>

import axios from "axios"
import Word from "@/components/Word"

export default {
  components : {
    Word
  },

  data() {
    return {
      wordList : [],
      english : "",
      turkish : ""
    }
    },
    methods : {

    },

    created() {
      axios.get("http://localhost:3000/wordList")
      .then(response => {
        for(let key in response.data){
          let word= {
            id : key,
            english : response.data[key].english,
            turkish : response.data[key].turkish
          }
            this.wordList.push(word)
        }
   
      })
      .catch()     
    },
    
}

</script>

<style>

</style>
