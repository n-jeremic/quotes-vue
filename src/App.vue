<template>
  <div id="main-div">
    <app-header :quotesNumber="quotes.length"></app-header>
    <app-quotes-input @quoteWasAdded="updateQuotesArray($event)"></app-quotes-input>
    <div class="row">
      <app-quote v-for="quote in quotes" :key="quote" :quote="quote" @quoteWasDeleted="deleteQuote"></app-quote>
    </div>
    <app-footer v-if="quotes.length > 0"></app-footer>
  </div>
</template>

<script>
import Header from "./components/Header.vue";
import Footer from "./components/Footer.vue";
import QuotesInput from "./components/QuotesInput.vue";
import Quote from "./components/Quote.vue";

export default {
  data() {
    return {
      quotes: ["Just some quote as an example!"]
    };
  },
  components: {
    "app-header": Header,
    "app-footer": Footer,
    "app-quotes-input": QuotesInput,
    "app-quote": Quote
  },
  methods: {
    updateQuotesArray(quote) {
      if (this.quotes.length === 10) {
        alert(
          "You have reached the quotes limit! Delete some in order to add more."
        );
        return;
      }

      this.quotes.push(quote);
    },
    deleteQuote(quote) {
      const index = this.quotes.findIndex(el => el === quote);
      this.quotes.splice(index, 1);
    }
  }
};
</script>

<style scoped>
#main-div {
  padding: 60px 100px;
}
</style>
