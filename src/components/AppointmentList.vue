<template>
    <div id="">
    <div v-for='(item,index) in appointments' v-bind:key='index'>
      <h4>{{item.petName}}</h4>
      <p>{{item.aptNotes}}</p>
    </div>
    </div>
</template>
<script>

export default {
  name: 'AppointmentList',
  props: ['appointments']
}

</script>