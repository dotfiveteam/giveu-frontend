<template>
  <div>
    <v-card>
      <v-container fluid grid-list-lg>
        <v-layout justify-center row wrap>
          <div v-for="event in events" v-bind:key="event.id">
            <EventItem v-bind:event="event"/>
          </div>
        </v-layout>
      </v-container>
    </v-card>
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
