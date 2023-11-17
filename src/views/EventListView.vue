<script setup>
import axios from 'axios'
import EventCard from '@/components/EventCard.vue'
import {ref} from 'vue'

const events = ref(
    null
//     [
//   {
//     id:1001,
//     category:'food',
//     title: 'Apple',
//     description:"Apple is a delicious food",
//     location:"Dhaka, Bangladesh",
//     date: '17-11-2023',
//     time: '8.40',
//     storeAllowed:true,
//     organizer:'Bangladesh'
//   },
//   {
//     id:1002,
//     category:'food',
//     title: 'Banana',
//     description:"Banana is a delicious food",
//     location:"Dhaka, Bangladesh",
//     date: '17-11-2023',
//     time: '8.40',
//     storeAllowed:true,
//     organizer:'Bangladesh'
//   },
//   {
//     id:1003,
//     category:'food',
//     title: 'Mango',
//     description:"Mango is a delicious food",
//     location:"Dhaka, Bangladesh",
//     date: '17-11-2023',
//     time: '8.40',
//     storeAllowed:true,
//     organizer:'Bangladesh'
//   },
//   {
//     id:1004,
//     category:'food',
//     title: 'Lichi',
//     description:"Lichi is a delicious food",
//     location:"Dhaka, Bangladesh",
//     date: '17-11-2023',
//     time: '8.40',
//     storeAllowed:true,
//     organizer:'Bangladesh'
//   },
// ]
)

axios.get('https://my-json-server.typicode.com/Code-Pop/Real-World_vue-3/events')
.then((response) => {
    events.value = response.data
})
.catch((error) => {
    console.log(error)
})
</script>

<template>
  <div class="events">
    <EventCard v-for="event in events" :key="event" :event="event" />
  </div>
</template>

<style scoped>
.events{
  display: flex;
  flex-direction: column;
  align-items: center;
}
</style>
