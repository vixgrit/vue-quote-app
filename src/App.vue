<template lang="html">
  <div class="container">
    <div class="row">
      <progress-bar :quotesAdded="quotesAdded"></progress-bar>
    </div>
    <div class="row">
      <quote-input></quote-input>
    </div>
  </div>
</template>

<script>
  import ProgressBar from './components/ProgressBar.vue'
  import QuoteInput from './components/QuoteInput.vue'
  export default {
    components: {
      'progress-bar': ProgressBar,
      'quote-input': QuoteInput
    },
    data() {
      return {
        quotesAdded: 3
      }
    }
  }
</script>

<style>
</style>
