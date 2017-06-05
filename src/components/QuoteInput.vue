<template lang="html">
  <div class="col-xs-12">
    <span>Quote</span>
    <textarea name="name" rows="4"></textarea>
    <button type="button" class="btn btn-primary">Add Quote</button>
  </div>
</template>

<script>
export default {

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
