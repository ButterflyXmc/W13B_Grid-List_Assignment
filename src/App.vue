<template>
  <div id="app">
    <TweetsComponent />
  </div>
</template>

<script>
import TweetsComponent from "@/components/TweetsComponent.vue";
export default {
  name: "App",
  components: {
    TweetsComponent,
  },
};
</script>

<style>
html {
  background-color: rgb(157, 214, 215);
}
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
