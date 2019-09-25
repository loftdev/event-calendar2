<template>
    <full-calendar :events="event" />
</template>

<script>
import FullCalendar from 'vue-fullcalendar';
export default {
    name: 'Calendar',
    props: ['event'],
    components: {
        FullCalendar
    },
}
</script>

<style scoped>

</style> 