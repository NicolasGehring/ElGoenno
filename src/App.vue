<template>
  <div id="app">
    <Header></Header>
    <!-- Services -->
    <Counter></Counter>
    <Timetable></Timetable>
    <Team></Team>
    <Donation></Donation>
    <Footer></Footer>
  </div>
</template>

<script>
import Header from "./components/Header";
import Counter from "./components/Counter";
import Team from "./components/Team";
import Footer from "./components/Footer";
import Timetable from "./components/Timetable";
import Donation from "./components/Donation";

export default {
  name: "app",
  components: {
    Timetable,
    Header,
    Counter,
    Team,
    Footer,
    Donation,
  },
};
</script>

<style>
#app {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

body {
  background: black;
}
</style>
