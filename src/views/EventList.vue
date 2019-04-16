<template>
  <div>
    
    <h1>Events for {{ user.user.name }}1</h1>
    <EventCard v-for="event in event.events" :key="event.id" :event="event"/>
    
  </div>
</template>

<script>
import EventCard from '@/components/EventCard.vue'
import EventCreate1 from '@/views/EventCreate.vue'
import { mapState } from 'vuex'

export default {
  components: {
    EventCard, EventCreate1
  },
  created() {
    this.perPage = 10 // Setting perPage here and not in data means it won't be reactive.
    // We don't need it to be reactive, and this way our component has access to it.

    this.$store.dispatch('event/fetchEvents', {
      perPage: this.perPage,
      page: this.page
    })
  },
  computed: {
    page() {
      return parseInt(this.$route.query.page) || 1
    },
    hasNextPage() {
      return this.event.eventsTotal > this.page * this.perPage
    },
    ...mapState(['event', 'user'])
  }
}
</script>
