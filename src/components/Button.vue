<template>
  <button :class="className" type="button" v-on:click="btnClick">{{ msg }}</button>
</template>

<script>
export default {
  name: 'Button',
  props: {
    msg: String,
    className: String
  },
  // define methods under the `methods` object
  methods: {
    btnClick: function (event) {
      alert('Hello !');
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
  @import './../assets/styles/button.scss';
</style>
