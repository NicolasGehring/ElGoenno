<template>
  <section id="services">
    <div class="container">
      <div class="row">
        <div class="col-lg-12 text-center">
          <h2 class="section-heading text-uppercase">Gönnerwoche?</h2>
          <div class="row text-center">
            <div class="col-md-12">
              <h3 class="section-subheading text-muted">
                Die Gönnerwoche ist die erste Septemberwoche jeden Jahres und dient einzig und alleine dem Zweck es sich einmal richtig gut gehen zu lassen.
                <br />
                <br />Nachdem man Klausuren, Stress und Arbeit hinter sich gelassen hat, soll diese Woche einen wieder an die guten Seiten im Leben erinnern. Wir freuen uns über jeden, der sich uns anschließt, um gemeinsam eine Woche voll Freunde und Gönnung zu feiern.
                <br />
                <br />Aus dem unten stehenden Timetable könnt ihr die einzelnen geplanten Aktivitäten sehen und bei Interesse einfach mitmachen.
                <br />
                <br />- Simon & Nicolas
              </h3>
            </div>
            <!-- <div class="col-md-6">
              <div class="row text-center">
                <div class="col-md-12">
                  <h4 class="service-heading">Biercounter</h4>
                  <p class="text-muted" v-if="beers">{{ beers.length }}</p>
                </div>
              </div>
            </div>-->
          </div>
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

<style lang="css" scoped></style>
