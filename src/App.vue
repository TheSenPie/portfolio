<template>
  <div id="app">
    <!-- <img alt="Vue logo" src="./assets/logo.png">
    <HelloWorld msg="Welcome to Your Vue.js App"/> -->
    <HomePage />
  </div>
</template>

<script>
import HomePage from './components/HomePage.vue'

export default {
	name: 'App',
	components: {
		HomePage
	}
}
</script>

<style src="./assets/sass/main.sass" lang="sass"></style>