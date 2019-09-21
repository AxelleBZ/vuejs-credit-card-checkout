<template>
  <div id="app">
    <div class="wrapper">
      <div class="wrapper-column">
        <img class="credit-card" alt="credit card" src="./assets/card.png">
      </div>
      <form class="card-form" action="">
        <div class="container-row">
         <label class="form-label" for="card-name">Cardholder Name</label>
         <Input type="text" placeholder="CARDHOLDER NAME" id="card-name"/>
        </div>

        <div class="container-row">
         <label class="form-label" for="card-number">Card Number</label>
         <Input type="text" placeholder="CARD NUMBER" id="card-number"/>
        </div>

        <div class="container-row container-columns">
          <div class="container-column">
           <label class="form-label" for="card-date">Exp date</label>
           <Input type="text" placeholder="EXP DATE" id="card-date"/>
          </div>

          <div class="container-column">
           <label class="form-label" for="card-cvc">CVC</label>
           <Input type="text" placeholder="CVC" id="card-cvc"/>
          </div>

           <div class="container-column image-visa">
             <img alt="Visa & Mastercard Logos" src="./assets/visa-mastercard.jpg">
           </div>
        </div>

        <div class="container-row">
          <p class="text-center">OR</p>
        </div>

        <div class="container-row">
          <Button msg="Pay with PayPal" className="btn-large" />
        </div>

        <div class="container-row container-columns">
          <div class="container-column column-half">
            <Button msg="Back" />
          </div>

          <div class="container-column column-half">
            <Button msg="Pay Now" className="btn-black" />
          </div>
        </div>
      </form>
    </div>
  </div>
</template>


<script>
import Button from './components/Button.vue'

export default {
  name: 'app',
  components: {
    Button
  }
}
</script>


<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

.wrapper {
  display: flex;
}

.wrapper-column {
  background: #e6c3c7;
  position: relative;
  width: 30%;
}

.credit-card {
  position: absolute;
  width: 100%;
  top: 0;
  bottom: 0;
  margin: auto;
  left: 20%;
}

.card-form {
  display: flex;
  flex-direction: column;
  align-items: flex-start;
  background: #f5f5f5;
  padding: 50px 100px;
  width: 70%;
}

.card-form .container-row {
  width: 100%;
}

.card-form .container-row > input{
  width: calc(100% - 40px);
}

.form-label {
  display: block;
  padding-left: 12px;
  padding-bottom: 10px;
}

.container-row {
  text-align: left;
  margin-bottom: 30px;
}

.container-columns {
  display: flex;
}

.container-column {
  display: flex;
  flex-direction: column;
  margin-right: 20px;
  justify-content: flex-end;
}

.container-column:last-child {
  margin-right: 0;
}

.column-half {
  width: 50%;
}

.container-row input {
  border-radius: 50px;
  padding: 10px 20px;
  color: grey;
  border: 1px solid grey;
}

.container-row input:focus {
  border-color: #2196F3;
  outline: none;
}

.text-center {
  width: 100%;
  text-align: center;
  margin: 0;
}


@media (max-width: 900px) {
  .wrapper {
    flex-direction: column;
  }

  .wrapper-column {
    width: 100%;
    height: 250px;
  }

  .credit-card {
    width: 40%;
    left: 30%;
  }

  .card-form {
    width: auto;
    padding: 30px;
  }
}

@media (max-width: 450px) {

.container-columns {
  flex-direction: column;
  display: flex;
}

.container-column {
  margin-top: 20px;
  margin-right: 0;
}

.container-column:first-child {
  margin-top: 0;
}


.image-visa {
  align-items: center;
}


.column-half {
  width: inherit;
}

.credit-card {
  width: 60%;
  left: 20%;
}

.wrapper-column {
  height: 200px;
}

}

</style>




