<template>
    <form >
        <div class="input-holder">
            <input type="text" placeholder="Event title" v-model="event.title" />
        </div>
        <div class="input-holder">
            <date-picker :placeholder="'Start date'" v-model="event.start" />
        </div>
        <div class="input-holder">
            <date-picker :placeholder="'End date'" v-model="event.end"/>
        </div>
        <div class="input-holder">
            <textarea placeholder="Event description" rows="4" v-model="event.data.description" ></textarea>
        </div>
        <div class="input-holder">
            <color-picker @colorPicked="selectColor" :color="event.cssClass" />
        </div>
        <div class="input-holder">
            <button @click.prevent="handleSubmit">Schedule</button>
        </div>

        <!-- Test the input data -->
        <p>{{ event }}</p>

    </form>
</template>

<script>
import DatePicker from 'vuejs-datepicker';
import format from 'date-fns/format';
import ColorPicker from './ColorPicker'
export default {
    name: 'EventForm',
    data() {
        return {
            event: {
                title: '',
                start: '',
                end: '',
                cssClass: '',
                data: {
                    description: ''
                }
            }
        }
    },
    methods: {
        handleSubmit() {
            this.event.start = format(this.event.start, 'YYYY-MM-DD');
            this.event.end = format(this.event.end, 'YYYY-MM-DD');
            this.$emit("eventAdded", this.event)

            // test if method is functioning
            this.event.title = 'method is working'
        }
    },
    components: {
        DatePicker,
        ColorPicker
    }
}
</script>

<style scoped>

</style>