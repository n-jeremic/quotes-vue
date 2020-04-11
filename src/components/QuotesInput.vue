<template>
  <div id="quotes-div">
    <h5>Quote</h5>
    <div class="form-group">
      <textarea class="form-control" rows="3" v-model="quoteText"></textarea>
    </div>
    <p class="text-center">
      <button class="btn btn-primary" @click="addQuote">Add Quote</button>
    </p>
  </div>
</template>

<script>
export default {
  data() {
    return {
      quoteText: ""
    };
  },
  methods: {
    addQuote() {
      if (this.quoteText.length === 0) {
        alert("You can't add an empty quote!");
        return;
      }
      this.$emit("quoteWasAdded", this.quoteText);
      this.quoteText = "";
    }
  }
};
</script>

<style scoped>
#quotes-div {
  margin: auto;
  padding: 40px 420px;
}
</style>