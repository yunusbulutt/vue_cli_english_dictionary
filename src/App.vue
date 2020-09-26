<template>
  <div id="contanier">
    <div class="row">
      <div class="col-md-8 offset-md-2 text-center">
        <div class="words-contanier">
          <div class="card" style="width: 56rem">
            <div class="card-header"><h3>English Dictionary</h3></div>
            <ul class="list-group list-group-flush">
              <li class="list-group-item">
                <h4>{{ word.english }}</h4>
              </li>
              <li class="list-group-item">
                <h4>{{ word.turkish }}</h4>
              </li>
              <li class="list-group-item">
                <button @click="nextWord" class="btn btn-primary btn-lg">
                  Öğrendim
                </button>
              </li>
            </ul>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import words from "@/assets/words";

export default {
  components: {},

  data() {
    return {
      wordList: [],
      english: "",
      turkish: "",
      wordIndex: Math.floor(Math.random() * words.wordList.length),
    };
  },
  methods: {
    nextWord() {
      this.wordIndex = Math.floor(Math.random() * words.wordList.length);
    },
  },

  computed: {
    word() {
      return this.wordList[this.wordIndex];
    },
  },

  created() {
    this.wordList = words.wordList;
  },
};
</script>

<style>
.card {
  margin-top: 30px;
}
</style>
