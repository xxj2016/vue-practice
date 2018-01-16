<template>
  <div id="app">
    <h1>在线翻译</h1>
    <h5 class="text-muted">简单 / 快捷 / 方便</h5>
    <translateForm v-on:transFormText="toTranslate"></translateForm>
    <translateOutput v-text="translatedResult"></translateOutput>
  </div>
</template>


<script>
import TranslateForm from "./components/TranslateForm";
import TranslateOutput from "./components/TranslateOutput";

export default {
  name: "app",
  data: function() {
    return {
      translatedResult: ""
    };
  },
  components: {
    TranslateForm,
    TranslateOutput
  },
  methods: {
    toTranslate: function(text, language) {
      this.$http
        .get(
          "https://translate.yandex.net/api/v1.5/tr.json/translate?key=trnsl.1.1.20180115T102034Z.678335b0e7a63407.507e45e111b0c0d210f3ee3892c85f78a20cf861&lang=" + language + "&text=" +
            text
        )
        .then(data => {
          console.log(data.body.text[0]);
          this.translatedResult = data.body.text[0];
        });
    }
  }
};
</script>

<style>
#app {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
