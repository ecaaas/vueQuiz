<template>
  <div class="hello">
    <h1 v-if="show">{{ msg }}</h1>

    <div v-for="(question, index) in quiz.questions" v-bind:key="question.id">
      <div v-show="index === questionIndex">
        <h4>{{ question.text }}</h4>
        <ol>
          <li v-for="response in question.responses" v-bind:key="response.id">
            <label>
              <input type="radio"
                     v-bind:value="response.choice"
                     v-bind:name="index"
                     v-model="picked"> {{ response.text }}
            </label>
          </li>
        </ol>

        <button v-on:click="check(question.correct, picked)">
          <span v-if="questionIndex == quiz.questions.length - 1">Finish</span>
          <span v-else>Next</span>
        </button>

        <h5>Benar: {{ totalCorrect }}</h5>
      </div>
    </div>

    <div v-show="questionIndex == quiz.questions.length">
      <h2>Kuis Selesai</h2>
      <p>Benar: {{ totalCorrect }} / {{ quiz.questions.length }}</p>
      <p>Nilai: {{ scoreCal() }}</p>
    </div>
  </div>
</template>

<script>
var quiz = {
  questions: [
    {
      text: " Teater Modern berkembang pada umumnya memperoleh pengaruh dari budaya?",
      responses: [
        {text : 'Primitifr', choice: 'A' },
        {text : 'Pendatang', choice: 'B' },
        {text : 'Barat', choice: 'C' },
        {text : 'Hedonisme', choice: 'D' },
      ],
      correct : 'D'
    },
    {
      text: "Berikut ini yang termasuk unsur sastra dalam sebuah drama adalah?",
      responses: [
        {text : 'Perwatakan ', choice: 'A' },
        {text : 'Tema', choice: 'B' },
        {text : 'Tata musik', choice: 'C' },
        {text : 'Penokohan', choice: 'D' },
      ],
      correct : 'C'
    },
    {
      text: "Salah satu contoh dari teater modern yang pernah di pentaskan oleh dramawan Indonesia adalah seperti dibawah ini, kecuali.. ",
      responses: [
        {text : 'Manusia Baru', choice: 'A' },
        {text : 'Dokter Bisma', choice: 'B' },
        {text : 'Taufan di atas asia', choice: 'C' },
        {text : 'Ramayana', choice: 'D' },
      ],
      correct : 'D'
    },
    {
      text: "Ciri khas dari teater modern, diantaranya dapat terlihat dari?",
      responses: [
        {text : 'Para pemainnya', choice: 'A' },
        {text : 'Penataan panggung dan dekorasi', choice: 'B' },
        {text : 'Bahasa yang digunakan', choice: 'C' },
        {text : 'Nilai yang disuguhkan', choice: 'D' },
      ],
      correct : 'B'
    },
    {
      text: "Tuan amin adalah saah satu karya teater moderen yang merupakan hasil karya?",
      responses: [
        {text : 'Amal Hamzah ', choice: 'A' },
        {text : 'El Hakim', choice: 'B' },
        {text : 'Sanoesi Pane', choice: 'C' },
        {text : 'Idrus', choice: 'D' },
      ],
      correct : 'A'
    },
  ]
};

export default {
  name: 'HelloWorld',
  props: {
    msg: String
  },
  data: function() {
    return {
      picked: '',
      show: true,
      quiz: quiz,
      questionIndex: 0,
      totalCorrect: 0,
      userResponses: Array(quiz.questions.length).fill(false)
    }
  },
  methods: {
    check(correct, picked) {
      if (correct === picked) this.totalCorrect++;
      this.questionIndex++;
    },
    scoreCal: function() {
      return (100 / quiz.questions.length) * this.totalCorrect;
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
