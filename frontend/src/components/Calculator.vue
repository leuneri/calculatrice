<template>
  <div>
    <h2>Calculator</h2>
    <form @submit.prevent="calculate">
      <input type="number" v-model="num1" placeholder="Number 1" required />
      <select v-model="operation">
        <option value="add">Addition</option>
        <option value="subtract">Subtraction</option>
        <option value="multiply">Multiplication</option>
        <option value="divide">Division</option>
      </select>
      <input type="number" v-model="num2" placeholder="Number 2" required />
      <button type="submit">Calculate</button>
    </form>
    <p v-if="result">Result: {{ result }}</p>
  </div>
</template>

<script>
export default {
  data() {
    return {
      num1: 0,
      num2: 0,
      operation: 'add',
      result: null,
    };
  },
  methods: {
    calculate() {
      // Send a request to the backend based on the selected operation and input values.
      // Update the 'result' property with the response from the backend.
        // Construct the URL for the appropriate operation
    if (isNaN(this.num1) || isNaN(this.num2)) {
        this.result = 'Please enter valid numbers.';
    } else if (this.operation === 'divide' && this.num2 === 0) {
      this.result = 'Cannot divide by zero.';
    } else {
      const url = `/api/calculator/${this.operation}?num1=${this.num1}&num2=${this.num2}`;

      // Send an HTTP GET request to the backend
      axios
        .get(url)
        .then((response) => {
          // Update the 'result' property with the response data
          this.result = response.data.result;
        })
        .catch((error) => {
          console.error(error);
          this.result = 'An error occurred. Please try again.';
          // Handle any errors or display an error message to the user.
        });
      };
    },
  },
};
</script>
