<template>
  <div>
    <v-container fluid grid-list-lg>
      <v-layout justify-center row wrap>
        <h3>{{channel_name}}</h3>
        <div v-for="video in videos" v-bind:key="video.id">
          <EventItem v-if="video.is_donate_video" v-bind:video="video"/>
        </div>
      </v-layout>
    </v-container>
  </div>
</template>

<script>
import EventItem from "./EventItem";

export default {
  name: "Events",
  components: {
    EventItem
  },
  props: ["channel_name", "videos"]
};
</script>

<style scoped>
</style>
