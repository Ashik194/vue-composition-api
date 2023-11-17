<script setup>
import EventListView from './EventListView.vue'
</script>

<template>
  <div class="events">
    <h1>Good Food, Good Health</h1>
    <!-- <EventCard v-for="event in events" :key="event" :event="event" /> -->
    <EventListView />
  </div>
</template>

<style scoped>
.events{
  display: flex;
  flex-direction: column;
  align-items: center;
}
</style>
