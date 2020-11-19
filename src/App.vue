<template>
  <div id="app">
    <Validator/>
  </div>
</template>

<script>
import Validator from './components/Validator';
export default {
  name: 'App',
  components: {
    Validator,
  },
};
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>