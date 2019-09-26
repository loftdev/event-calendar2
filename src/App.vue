<template>
  <div id="app">
    <div class="main">
      <div class="clendar-holder">
        <calendar :events="events" />

        <!-- Test events data if it is change -->
        <p>{{ events }}</p>
        
      </div>
      <div class="event-holder">
        <event-form @eventAdded="events.push($event)" />
      </div>
    </div>
  </div>
</template>

<script>
import Calendar from "./components/Calendar"
import EventForm from "./components/EventForm"
export default {
  name: 'app',
  data(){
    return {
      events: [{
        title: 'event1',
        start: '2019-09-27',
        cssClass: 'blue',
        YOUR_DATA: {}
        },
        {
        title: 'event2',
        start: '2019-09-28',
        end: '2019-09-30',
        cssClass  : ['orange']
      }] 
    }
  },
  components: {
    Calendar,
    EventForm
  },
  methods: {
    addEvent(x) {
      this.events.push(x)
    }
  }
}
</script>

<style>

</style>
