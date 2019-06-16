<template>
  <div>
    <div v-for="event in events" v-bind:key="event.id">
      <EventItem v-bind:event="event"/>
    </div>
  </div>
</template>

<script>
import EventItem from "./EventItem";

export default {
  name: "Events",
  components: {
    EventItem
  },
  props: ["events"]
};
</script>

<style scoped>
</style>
