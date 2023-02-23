<template>
  <div id="app">
    <link rel="stylesheet" href="https://cdn.jsdelivr.net/npm/bootstrap@4.0.0/dist/css/bootstrap.min.css" integrity="sha384-Gn5384xqQ1aoWXA+058RXPxPg6fy4IWvTNh0E263XmFcJlSAwiGgFAW/dAiS6JXm" crossorigin="anonymous">
    <WeatherBot />
  </div>
</template>


<script>
import WeatherBot from "./components/WeatherBot.vue";

export default {
  name: "App",
  components: {
    WeatherBot,
  },
};
</script>