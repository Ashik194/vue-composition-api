<script setup>
import EventService from '@/services/EventService.js'
import EventCard from '@/components/EventCard.vue'
import {onMounted, ref} from 'vue'

const events = ref(null)

onMounted(()=>{
    EventService.getEvents()
    .then((response) => {
        events.value = response.data
    })
    .catch((error) => {
        console.log(error)
    })
})

</script>

<template>
  <div class="events">
    <EventCard v-for="event in events" :key="event" :event="event" />
  </div>
</template>

<style >
.events{
  display: flex;
  flex-direction: column;
  align-items: center;
}
</style>
