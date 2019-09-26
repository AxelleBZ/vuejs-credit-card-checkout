<template>
  <button :class="className" :type="buttonType">{{ msg }}</button>
</template>

<script>
  export default {
    name: 'Button',
    props: {
      msg: String,
      className: String,
      buttonType: String
    }
  }
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
  @import './../assets/styles/button.scss';
</style>
