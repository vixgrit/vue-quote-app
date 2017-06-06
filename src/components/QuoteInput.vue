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
  methods: {
    submitQuote() {
      const quoteBox = document.querySelector('.quoteBox');
      eventBus.$emit('quoteSubmitted', quoteBox.value);
      quoteBox.value = '';
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
  }

  button {
    margin: 30px auto;
    display: block;
  }
</style>
