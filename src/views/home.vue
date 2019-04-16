<template>
  <div>
      <h1>Este es el home</h1>
    <EventCreate1></EventCreate1>
    <hr>
    <EventList></EventList>
    
    <hr>
    <EventList></EventList>
    
  </div>
</template>

<script>
import EventCard from '@/components/EventCard.vue'
import EventCreate1 from '@/views/EventCreate.vue'
import EventList from '@/views/EventList.vue'
import { mapState } from 'vuex'

export default {
  components: {
    EventCard, EventCreate1,EventList
  }
}
</script>
