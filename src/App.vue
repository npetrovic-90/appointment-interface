<template>
  <div id='main-app' class='container'>
    <h4>{{title}}</h4>
    <font-awesome-icon icon='plus' class='me-2'></font-awesome-icon>Add appointment
  </div>
</template>

<script>
import { FontAwesomeIcon } from '@fortawesome/vue-fontawesome'
export default {
  name: 'MainApp',
  data: function() {
    return {
      title: "Appointment list"
    }
  },
  components: {
    FontAwesomeIcon
  }

}
</script>

