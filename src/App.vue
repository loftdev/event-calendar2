<template>
  <div id="app">
    <div class="main">
      <div class="clendar-holder">
        <calendar />
      </div>
      <div class="event-holder">

      </div>
    </div>
  </div>
</template>

<script>
import Calendar from "./components/Calendar"
import EventForm from "./components/EventForm"
export default {
  name: 'app',
  components: {
    Calendar
  }
}
</script>

<style>

</style>
