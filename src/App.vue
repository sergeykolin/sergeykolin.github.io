<template>
  <div id="app">
    <Navbar/>
    <Dashboard/>
    <FooterApp/>
  </div>
</template>

<script>
import Navbar from './components/Navbar.vue';
import FooterApp from './components/FooterApp.vue';
import Dashboard from './components/Dashboard.vue'

export default {
  name: 'App',
  components: {
    Dashboard,
    Navbar,
    FooterApp,
}
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  background-image: url(https://static.tildacdn.com/tild3935-3535-4335-a333-383831323963/DubaiMapBlur.png);
  background-repeat: no-repeat;
  background-position: center;
  -webkit-background-size: cover;
  background-size: cover;
  min-height: 100%;
  height: 100vh;
  display: grid;
}
</style>
