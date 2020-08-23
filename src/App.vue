<template>
  <div id="app">
    <Header></Header>
    <!-- Services -->
    <Counter></Counter>
    <Timetable></Timetable>
    <!-- Portfolio Grid -->
    <Portfolio></Portfolio>
    <Team></Team>
    <Contact></Contact>
    <Footer></Footer>
  </div>
</template>

<script>
import Portfolio from "./components/Portfolio";
import Header from "./components/Header";
import Counter from "./components/Counter";
import Team from "./components/Team";
import Footer from "./components/Footer";
import Contact from "./components/Contact";
import Timetable from "./components/Timetable";

export default {
  name: "app",
  components: {
    Portfolio,
    Timetable,
    Header,
    Counter,
    Team,
    Footer,
    Contact,
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
