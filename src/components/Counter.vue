<template>
  <section id="services">
    <div class="container">
      <div class="row">
        <div class="col-lg-12 text-center">
          <h2 class="section-heading text-uppercase">Was bisher geschah</h2>
          <h3 class="section-subheading text-muted">Lorem ipsum dolor sit amet consectetur.</h3>
        </div>
      </div>
      <div class="row text-center">
        <div class="col-md-4">
          <span class="fa-stack fa-4x">
            <i class="fas fa-circle fa-stack-2x text-primary"></i>
            <i class="fas fa-shopping-cart fa-stack-1x fa-inverse"></i>
          </span>
          <h4 class="service-heading">Biercounter</h4>
          <p class="text-muted" v-if="beers">{{beers.length}}</p>
        </div>

        <div class="col-md-4">
          <span class="fa-stack fa-4x">
            <i class="fas fa-circle fa-stack-2x text-primary"></i>
            <i class="fas fa-laptop fa-stack-1x fa-inverse"></i>
          </span>
          <h4 class="service-heading">Responsive Design</h4>
          <p class="text-muted">
            Lorem ipsum dolor sit amet, consectetur adipisicing elit. Minima
            maxime quam architecto quo inventore harum ex magni, dicta impedit.
          </p>
        </div>
        <div class="col-md-4">
          <span class="fa-stack fa-4x">
            <i class="fas fa-circle fa-stack-2x text-primary"></i>
            <i class="fas fa-lock fa-stack-1x fa-inverse"></i>
          </span>
          <h4 class="service-heading">Web Security</h4>
          <p class="text-muted">
            Lorem ipsum dolor sit amet, consectetur adipisicing elit. Minima
            maxime quam architecto quo inventore harum ex magni, dicta impedit.
          </p>
        </div>
      </div>
    </div>
  </section>
</template>

<script>
import axios from "axios";
export default {
  data() {
    return {
      beers: [],
      errors: [],
    };
  },
  async created() {
    try {
      const response = await axios.get(
        `http://jsonplaceholder.typicode.com/posts`
      );
      this.posts = response.data;
      console.log(response);
    } catch (e) {
      this.errors.push(e);
    }
  },
  async mounted() {
    // get event id for El Goenno Grande
    const event_id_res = await axios.get(
      "https://beercounter-78aae.firebaseio.com/egg_event_id.json"
    );
    // get all beers
    var beers_res = await axios.get(
      "https://beercounter-78aae.firebaseio.com/beers.json"
    );
    // filter beers by El Goenno Grande Event
    this.beers = beers_res.data.filter(
      (beer) => beer.eventId == event_id_res.data
    );
  },
};
</script>

<style lang="css" scoped>
</style>