<template>
  <div id="app">
    <video-parse />
  </div>
</template>

<script>
import VideoParse from "./views/VideoParse";

export default {
  name: "App",
  components: {
    VideoParse
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
  margin-top: 20px;
}
</style>
