<template>
  <div id="app">
    <Button @updateQuote="fetchNewQuote" />
    <Quote :quote="kanyeQuote" />
  </div>
</template>

<script>
import Button from "./components/Button.vue";
import Quote from "./components/Quote.vue";

export default {
  name: "App",
  components: {
    Button,
    Quote
  },
  data: function() {
    return {
      kanyeQuote: "Click the above button to generate a Quote"
    };
  },
  methods: {
    fetchNewQuote: function() {
      let appComponent = this;
      let ajax = new XMLHttpRequest();
      ajax.onreadystatechange = function() {
        if (this.status == 200 && this.readyState == 4) {
          let myQuote = JSON.parse(this.responseText);
          appComponent.kanyeQuote = myQuote.quote;
        }
      };
      ajax.open("GET", "https://api.kanye.rest/", true);
      ajax.send();
    }
  }
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>