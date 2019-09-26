<template>
    <full-calendar :events="events" />
</template>

<script>
import FullCalendar from 'vue-fullcalendar';
export default {
    name: 'Calendar',
    props: ['events'],
    components: {
        FullCalendar
    },
}
</script>

<style scoped>

</style> 