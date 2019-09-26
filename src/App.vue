<template>
  <div id="app">
    <div class="wrapper">
      <div class="wrapper-column">
        <img class="credit-card" alt="credit card" src="./assets/card.png">
      </div>
      <CardForm />
    </div>
  </div>
</template>


<script>
  import CardForm from './components/CardForm.vue'

  export default {
    name: 'app',
    components: {
      CardForm
    }
  }
</script>

<style scoped>
  @import './assets/styles/app.scss';
</style>

