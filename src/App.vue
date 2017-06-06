<template lang="html">
  <div class="container">
    <div class="row">
      <progress-bar></progress-bar>
    </div>
    <div class="row">
      <quote-input></quote-input>
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
  import Quote from './components/Quote.vue';
  export default {
    components: {
      'progress-bar': ProgressBar,
      'quote-input': QuoteInput,
      'quote-display': QuoteDisplay
    },
    data() {
      return {
        quotesAdded: ['This is a long test quote'],
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
