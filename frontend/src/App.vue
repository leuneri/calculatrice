<template>
  <div id="app">
    <Calculator />
  </div>
</template>

<script>
import Calculator from './components/Calculator.vue';

export default {
  components: {
    Calculator,
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 20px;
}

h2 {
  font-size: 1.5em;
  margin-bottom: 10px;
}

form {
  display: flex;
  flex-direction: column;
  align-items: center;
}

input[type="number"] {
  width: 100%;
  padding: 10px;
  margin: 5px;
  border: 1px solid #ccc;
  border-radius: 4px;
  font-size: 1em;
}

select {
  width: 100%;
  padding: 10px;
  margin: 5px;
  border: 1px solid #ccc;
  border-radius: 4px;
  font-size: 1em;
}

button {
  padding: 10px 20px;
  margin: 10px;
  background-color: #3498db;
  color: white;
  border: none;
  border-radius: 4px;
  font-size: 1em;
  cursor: pointer;
}

button:hover {
  background-color: #2980b9;
}

p {
  font-size: 1.2em;
  margin-top: 20px;
}
</style>