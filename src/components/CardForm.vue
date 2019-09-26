<template>
  <form
    class="card-form"
    action=""
    @submit="validateForm"
  >
    <p class="error-msg" v-if="errors.length">
      <b>{{ errors[0] }}</b>
    </p>
    <div class="container-row">
      <label class="form-label" for="card-name">Cardholder Name</label>
      <ValidationProvider rules="required" v-slot="{ errors, classes }" class="input-wrapper">
        <input v-model="cardName" :class="classes" type="text" placeholder="CARDHOLDER NAME" id="card-name"/>
        <span class="error-msg">{{ errors[0] }}</span>
      </ValidationProvider>
    </div>

    <div class="container-row">
     <label class="form-label" for="card-number">Card Number</label>
     <ValidationProvider rules="required" v-slot="{ errors, classes }" class="input-wrapper">
        <input v-model="cardNumber" :class="classes" type="text" placeholder="CARD NUMBER" id="card-number"/>
        <span class="error-msg">{{ errors[0] }}</span>
      </ValidationProvider>
    </div>

    <div class="container-row container-columns">
      <div class="container-column">
       <label class="form-label" for="card-date">Exp date</label>
        <ValidationProvider rules="required" v-slot="{ errors, classes }" class="input-wrapper">
        <input v-model="cardDate" :class="classes" type="text" placeholder="EXP DATE" id="card-date"/>
        <span class="error-msg">{{ errors[0] }}</span>
      </ValidationProvider>
    </div>

    <div class="container-column">
      <label class="form-label" for="card-cvc">CVC</label>
        <ValidationProvider rules="required" v-slot="{ errors, classes }" class="input-wrapper">
        <input v-model="cardCvc" :class="classes" type="text" placeholder="CVC" id="card-cvc"/>
        <span class="error-msg">{{ errors[0] }}</span>
      </ValidationProvider>
    </div>

       <div class="container-column image-visa">
         <img alt="Visa & Mastercard Logos" src="../assets/visa-mastercard.jpg">
       </div>
    </div>

    <div class="container-row">
      <p class="text-center">OR</p>
    </div>

    <div class="container-row">
      <Button msg="Pay with PayPal" buttonType="button" className="btn-large" />
    </div>

    <div class="container-row container-columns">
      <div class="container-column column-half">
        <Button msg="Back" buttonType="button" />
      </div>

      <div class="container-column column-half">
        <Button msg="Pay Now" buttonType="submit" className="btn-black" />
      </div>
    </div>
  </form>
</template>

<script>
  import Button from '../components/Button.vue';
  import Vue from 'vue';
  import { ValidationProvider, extend } from 'vee-validate';

  extend('required', {
    validate: value => !!value,
    message: 'Ce champs est requis'
  });

  Vue.component('ValidationProvider', ValidationProvider);


  export default {
    name: 'CardForm',
    components: {
      Button
    },
    data:() => ({
      cardName: null,
      cardNumber: null,
      cardDate: null,
      cardCvc: null,
      errors: []
    }),
    methods: {
      validateForm: function (event) {

        this.errors = [];

        if (this.cardName && this.cardNumber && this.cardDate && this.cardCvc) {
          return true;
        } else {
          this.errors.push('All the fields are required!')
        }

        event.preventDefault();
      }
    }
  }
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
  @import './../assets/styles/card-form.scss';
</style>
