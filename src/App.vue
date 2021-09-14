<template>
  <div id="main-app" class="container">
    <appointment-list v-bind:appointments='appointments'></appointment-list>
  </div>
</template>

<script>
// import { FontAwesomeIcon } from "@fortawesome/vue-fontawesome";
import  AppointmentList  from './components/AppointmentList'
import axios from 'axios'
export default {
  name: "MainApp",
  data: function() {
    return {
      title: "Appointment list",
      appointments: []
    };
  },
  components: {
    AppointmentList
  },
  mounted() {
    axios.get('./data/appointments.json')
          .then(response=>(this.appointments = response.data))
  }
};
</script>
