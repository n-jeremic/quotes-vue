<template>
  <div>
    <h2 class="mb-4">Quotes Added</h2>
    <div class="progress">
      <div class="progress-bar" role="progressbar" :style="{ 'width': quotesNumber + '0%' }">
        <span v-if="quotesNumber > 0">{{ quotesNumber }} / 10</span>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  props: {
    quotesNumber: Number
  }
};
</script>

<style scoped>
.progress {
  height: 25px;
}
</style>