<script setup>
import EventService from '@/services/EventService.js'
import {onMounted, ref} from 'vue'

const propps = defineProps({
    id: {
        required:true
    }
})
const event = ref(null)

onMounted(()=>{
    EventService.getEvent(propps.id)
    .then((response) => {
        event.value = response.data
    })
    .catch((error) => {
        console.log(error)
    })
})

</script>

<template>
  <div class="events" v-if="event">
        <h2>{{ event.title }}</h2>
        <p>@{{ event.time }} on {{ event.date }}</p>
        <p>{{ event.description }}</p>
  </div>
</template>


<style scoped>
.event-card{
    padding: 20px;
    width: 250px;
    cursor: pointer;
    border: 1px solid #39495c;
    margin-bottom: 18px;
}
.event-card:hover{
    transform: scale(1.01);
    box-shadow: 0 3px 12px 0 rgba(0, 0, 0, 0.2);
}
</style>