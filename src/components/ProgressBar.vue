<template lang="html">
  <div class="col-xs-12">
    <h3>Quotes Added</h3>
    <div class="progress-bar">
      <div class="progress-status" :style="progressStatus">
        <span v-if="quotesAdded > 0" class="progress-text">{{quotesAdded}} / 10</span>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  props: ['quotesAdded'],
  data() {
    return {
      progressStatus: {
        width: this.quotesAdded / 10 * 100 + '%'
      }
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
    width: 0px;
    height: 24px;
    background-color: #6ca6cd;
  }

  .progress-text {
    font-size: 18px;
  }
</style>
