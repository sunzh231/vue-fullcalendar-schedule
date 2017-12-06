<template>
  <div class="hello">
    <div id="calendar-wrap">
      <full-calendar
        ref="calendar"
        :config="config"
        :events="events"

        @event-selected="eventSelected">
      </full-calendar>
    </div>
  </div>
</template>

<script>
import moment from 'moment'
import 'fullcalendar/dist/fullcalendar.css'
import {FullCalendar} from 'vue-full-calendar'
import 'fullcalendar/dist/locale-all.js'

export default {
  data () {
    return {
      config: {
        header: {
          left: 'prev,next',
          center: 'title',
          right: ''
        },
        locale: 'zh-cn',
        defaultView: 'month',
        droppable: false,
        // drop(...args) {
        //   console.log(args)
        //   //handle drop logic in parent
        // },
      },
      events: [
        {
          id: 1,
          title: 'event1',
          start: moment().hours(12).minutes(0),
        },
        {
          id: 2,
          title: 'event2',
          start: moment().add(-1, 'days'),
          end: moment().add(1, 'days'),
          allDay: true,
        },
        {
          id: 3,
          title: 'event3',
          start: moment().add(2, 'days'),
          end: moment().add(2, 'days').add(6, 'hours'),
          allDay: false,
        }
      ],
      eventSources: [
        {
          events(start, end, timezone, callback) {
            // self.$http.get(`/myFeed`, {timezone: timezone}).then(response => {
            //   callback(response.data.data)
            // })
          },
          color: 'yellow',
          textColor: 'black',
        },
        {
          events(start, end, timezone, callback) {
            // self.$http.get(`/anotherFeed`, {timezone: self.timezone}).then(response => {
            //   callback(response.data.data)
            // })
          },
          color: 'red',
        },
      ]
    }
  },
  mounted () {

  },
  methods: {
    eventSelected () {

    }
  },
  components: {
    FullCalendar
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

</style>
