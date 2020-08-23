<template>
  <div>
    <h2>Timetable</h2>
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
          >
            {{ act }}
          </td>
        </tr>
      </tbody>
    </table>
  </div>
</template>

<script>
export default {
  data() {
    return {
      events: [
        {
          type: "morgens",
          activities: [
            { name: "Morgens", type: "all" },
            "---",
            "Chill",
            "GranFondo",
            "Chill",
            "Chill",
            "Chill",
            "Klettersteig",
          ],
        },
        {
          type: "mittags",
          activities: [
            "Mittags",
            "---",
            "Chill",
            "GranFondo",
            "Chill",
            "Chill",
            "Chill",
            "Klettersteig",
          ],
        },
      ],
    };
  },
};
</script>

<style scoped>
table {
  width: 100%;
  table-layout: fixed;
}
table,
th,
tr,
td {
  border: 1px solid #000;
}
.all {
  background-color: aqua;
}
</style>
