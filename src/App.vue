<template>
  <div id="app">
    <img src="./assets/logo.png">
    <router-view :personprop="person" @datachanged="handleDatachanged"/>
  </div>
</template>

<script>
export default {
  name: "App",
  data: function() {
    return {
      person: {
        name: "Terje",
        birthYear: 1975
      }
    };
  },
  methods: {
    handleDatachanged: function(personData) {
      this.person.name = personData.name;
      this.person.birthYear = personData.birthYear;
    }
  }
};
</script>

<style>
#app {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
