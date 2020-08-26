<template>
  <section class="bg-light" id="timetable">
    <div class="container">
      <div class="row">
        <div class="col-lg-12 text-center">
          <h2 class="section-heading text-uppercase">Timetable</h2>
          <h3 class="section-subheading text-muted">
            Bei Fragen bezüglich genauer Uhrzeiten bitte einen von uns
            kontaktieren.
            <br />
            <b>
              Rot -> Teilnahme nichtmehr möglich Gelb -> Teilnehmerzahl begrenz
              bei interesse melden
            </b>
          </h3>
        </div>
      </div>
      <div class="row" style="overflow-x:auto;">
        <table id="tableId">
          <thead>
            <tr>
              <th>Wann?</th>
              <th>Montag</th>
              <th>Dienstag</th>
              <th>Mittwoch</th>
              <th>Donnerstag</th>
              <th>Freitag</th>
              <th>Samstag</th>
              <th>Sonntag</th>
            </tr>
          </thead>
          <tbody>
            <tr v-for="item in events" v-bind:key="item.type">
              <td
                v-for="act in item.activities"
                v-bind:key="act"
                v-bind:class="act.type"
              >{{ act.name }}</td>
            </tr>
          </tbody>
        </table>
      </div>
    </div>
  </section>
</template>

<script>
var jsonEventData = require("./events.json");
export default {
  data() {
    return jsonEventData;
  },
};
</script>

<style scoped>
table {
  width: 1000px;
  table-layout: fixed;
  margin: auto;
}
table,
th,
tr,
td {
  border: 1px solid #000;
}

tr {
  height: 75px;
  width: 75px;
}
.restricted {
  background-color: yellow;
}
.closed {
  background-color: red;
}
</style>
