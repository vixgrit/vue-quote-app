<template>
  <div class="container">
    <div class="row">
      <progress-bar :quotesAdded="quotesAdded"></progress-bar>
    </div>
  </div>
</template>

<script>
  import ProgressBar from './components/ProgressBar.vue'
  export default {
    components: {
      'progress-bar': ProgressBar
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
