<template>
  <div id="app">
    <translateForm v-on:transFormText="toTranslate"></translateForm>
    <translateOutput v-bind:result="transFormText"></translateOutput>
  </div>
</template>


<script>
import TranslateForm from "./components/TranslateForm";
import TranslateOutput from "./components/TranslateOutput";

export default {
  name: "app",
  data: function() {
    return {
      transFormText: ""
    };
  },
  components: {
    TranslateForm,
    TranslateOutput
  },
  methods: {
    toTranslate: function(text) {
      this.$http.get(
        "https://translate.yandex.net/api/v1.5/tr.json/translate?key=trnsl.1.1.20180115T102034Z.678335b0e7a63407.507e45e111b0c0d210f3ee3892c85f78a20cf861&lang=en&text=" + text
      ).then(data => {
        console.log(data.body.text[0]);
        this.transFormText = data.body.text[0];
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
