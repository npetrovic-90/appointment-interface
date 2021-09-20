<template>
  <div id="main-app" class="container">
    <div class="row justify-content-center">
      <appointment-list
        v-bind:appointments="appointments"
        @remove="removeItem"
      ></appointment-list>
    </div>
  </div>
</template>

<script>
// import { FontAwesomeIcon } from "@fortawesome/vue-fontawesome";
import AppointmentList from "./components/AppointmentList";
import axios from "axios";
import _ from "lodash";
export default {
  name: "MainApp",
  data: function () {
    return {
      title: "Appointment list",
      appointments: [],
    };
  },
  components: {
    AppointmentList,
  },
  mounted() {
    axios
      .get("./data/appointments.json")
      .then((response) => (this.appointments = response.data));
  },
  methods: {
    removeItem: function (apt) {
      this.appointments = _.without(this.appointments, apt);
    },
  },
};
</script>
