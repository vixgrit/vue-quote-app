<template lang="html">
  <div>
    <span>Quote</span>
    <textarea class="quoteBox" name="name" rows="4"></textarea>
    <button @click="submitQuote" type="button" class="btn btn-primary">Add Quote</button>
  </div>
</template>

<script>
import { eventBus } from './../main';
export default {
  props: ['numOfQuotes', 'maxQuotes'],
  methods: {
    submitQuote() {
      const quoteBox = document.querySelector('.quoteBox');
      if (this.numOfQuotes >= this.maxQuotes) {
        quoteBox.value = '';
        return alert('You\'ve reached the quote limit! Please delete a quote first.');
      }
      else if (quoteBox.value.trim() === ''){
        return alert('Your quote must contain some text!');
      }
      else {
        eventBus.$emit('quoteSubmitted', quoteBox.value);
        quoteBox.value = '';
      }
    }
  }
}
</script>

<style lang="css" scoped>
  div {
    margin-top: 30px;
  }

  span {
    font-size: 14px;
    font-weight: bold;
    margin-left: 20%;
  }

  textarea {
    width: 60%;
    display: block;
    margin: 0 auto;
    resize: none;
    border: 1px solid #ddd;
  }

  button {
    margin: 30px auto;
    display: block;
  }
</style>
