<template lang="html">
  <div class="container">
    <div class="row">
      <progress-bar :quoteCount="quotesAdded.length" :maxQuotes="maxQuotes"></progress-bar>
    </div>
    <div class="row">
      <quote-input :numOfQuotes="quotesAdded.length" :maxQuotes="maxQuotes"></quote-input>
      <quote-display :quotes="quotesAdded" @quoteDeleted="deleteQuote"></quote-display>
      <div class="col-sm-12 text-center">
        <div class="alert alert-info">Info: Click on a quote to delete it.</div>
      </div>
    </div>
  </div>
</template>

<script>
  import { eventBus } from './main';
  import ProgressBar from './components/ProgressBar.vue';
  import QuoteInput from './components/QuoteInput.vue';
  import QuoteDisplay from './components/QuoteDisplay.vue';
  export default {
    components: {
      'progress-bar': ProgressBar,
      'quote-input': QuoteInput,
      'quote-display': QuoteDisplay
    },
    data() {
      return {
        quotesAdded: ['An example quote...'],
        maxQuotes: 10
      }
    },
    methods: {
      deleteQuote(index) {
        this.quotesAdded.splice(index, 1);
      }
    },
    created() {
      eventBus.$on('quoteSubmitted', (quote) => {
        this.quotesAdded.push(quote);
      });
    }
  }
</script>

<style>
</style>
