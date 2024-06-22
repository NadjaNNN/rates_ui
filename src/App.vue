<template>
  <div id="app">
    <ExchangeRatesForm />
  </div>
</template>

<script>
import ExchangeRatesForm from './components/ExchangeRatesForm.vue';

export default {
  name: 'App',
  components: {
    ExchangeRatesForm
  }
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
