<script setup>
import { RouterLink, RouterView } from 'vue-router'
</script>

<template>
  <div id="layout">
  <header>
    <div class="wrapper">
      <nav>
        <RouterLink :to="{name:'event-list'}">Event List </RouterLink> | 
        <RouterLink :to="{name:'about'}">About</RouterLink>
      </nav>
    </div>
  </header>
</div>
  <RouterView />
</template>

<style >
#layout{
  font-family: Arial, Helvetica, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-font-smoothing:grayscale;
  text-align: center;
  color: #2c3e50;
}
nav{
  padding: 30px;
}
nav a{
  font-weight: bold;
  color: #2c3e50;
}
nav a.router-link-exact-active{
  color: #2c3e50;
}
</style>
