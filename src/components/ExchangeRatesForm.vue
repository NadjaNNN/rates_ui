<template>
  <div>
    <form @submit.prevent="fetchRates">
      <div>
        <label for="amount">Amount:</label>
        <input type="number" v-model="amount" id="amount" required>
      </div>
      <div>
        <label for="from">From:</label>
        <input type="text" v-model="fromCurrency" id="from" required>
      </div>
      <div>
        <label for="to">To:</label>
        <input type="text" v-model="toCurrency" id="to" required>
      </div>
      <button type="submit">Convert</button>
    </form>
    <div v-if="result">
      <p>Converted Amount: {{ result }}</p>
    </div>
  </div>
</template>

<script>
import axios from 'axios';

export default {
  data() {
    return {
      amount: 0,
      fromCurrency: '',
      toCurrency: '',
      result: null
    };
  },
  methods: {
    async fetchRates() {
      try {
        const response = await axios.get('http://localhost:8080/conversions', {
          params: {
            amount: this.amount,
            from: this.fromCurrency,
            to: this.toCurrency
          }
        });
        this.result = response.data;
      } catch (error) {
        console.error(error);
      }
    }
  }
};
</script>

<style scoped>
form {
  margin-bottom: 20px;
}
</style>
