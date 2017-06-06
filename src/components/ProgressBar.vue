<template lang="html">
  <div class="col-xs-12">
    <h3>Quotes Added</h3>
    <div class="progress-bar">
      <div v-if="quoteCount > 0" class="progress-status" :style="{ width: progressStatus}">
        <span class="progress-text">{{quoteCount}} / {{maxQuotes}}</span>
      </div>
      <div v-else>
        <span :style="noQuotes">0 / 10</span>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  props: ['quoteCount', 'maxQuotes'],
  data() {
    return {
      noQuotes: {
        'text-align': 'center',
        'color': 'black',
        'line-height': '24px'
      }
    }
  },
  computed: {
    progressStatus() {
      return this.quoteCount / this.maxQuotes * 100 + '%';
    }
  }
}
</script>

<style lang="css" scoped>
  .progress-bar {
    border-radius: 15px;
    height: 24px;
    width: 100%;
    background-color: #eee;
  }

  .progress-status {
    border-radius: 15px;
    height: 24px;
    background-color: #6ca6cd;
    transition: width 1s;
  }

  .progress-text {
    font-size: 18px;
  }
</style>
