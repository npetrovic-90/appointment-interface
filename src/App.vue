<template>
  <div id="main-app" class="container">
    <h4>{{ title }}</h4>
    <font-awesome-icon icon="plus" class="me-2"></font-awesome-icon>Add
    appointment
    <div v-for='(item,index) in appointments' v-bind:key='index'>
      <h4>{{item.petName}}</h4>
      <p>{{item.aptNotes}}</p>
    </div>
  </div>
</template>

<script>
import { FontAwesomeIcon } from "@fortawesome/vue-fontawesome";
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
    FontAwesomeIcon,
  },
  mounted() {
    axios.get('./data/appointments.json')
          .then(response=>(this.appointments = response.data))
  }
};
</script>
