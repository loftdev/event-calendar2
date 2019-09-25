<template>
  <div id="app">
    <div class="main">
      <div class="clendar-holder">
        <calendar :event="event" />
      </div>
      <div class="event-holder">
        <event-form @eventAdded="event = $event" />
      </div>
    </div>
  </div>
</template>

<script>
import Calendar from "./components/Calendar"
import EventForm from "./components/EventForm"
export default {
  name: 'app',
  data() {
    return {
      event: []
    }
  },
  components: {
    Calendar,
    EventForm
  }
}
</script>

<style>

</style>
