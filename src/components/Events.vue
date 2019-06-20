<template>
  <div>
    <v-container fluid grid-list-lg>
      <v-layout justify-center row wrap>
        <v-expansion-panel>
          <v-expansion-panel-content>
            <template v-slot:header>
              <div class="subheading font-weight-bold">{{channel_name}}</div>
            </template>
            <v-layout row wrap>
              <v-flex v-for="video in videos" v-bind:key="video.id" xs12>
                <!-- <EventItem v-if="video.is_donate_video" v-bind:video="video"/> -->
                <EventItem v-bind:video="video"/>
              </v-flex>
            </v-layout>
          </v-expansion-panel-content>
        </v-expansion-panel>
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
