<template>
  <div class="col-lg-3 mb-4">
    <div class="card shadow" @click="deleteQuote">
      <div class="card-body text-center">{{ quote }}</div>
    </div>
  </div>
</template>

<script>
export default {
  props: {
    quote: String,
    index: Number
  },
  methods: {
    deleteQuote() {
      this.$emit("quoteWasDeleted", this.index);
    }
  }
};
</script>

<style scoped>
.card:hover {
  cursor: pointer;
  background-color: lightgray;
}

.card-body {
  font-family: "Arizonia";
  padding: 10px 20px;
  font-size: 35px;
  color: orchid;
}
</style>