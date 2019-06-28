<template>
  <div>
    <v-container fluid grid-list-sm pa-0>
      <v-card>
        <v-layout justify-center row wrap>
          <v-flex xs12>
            <v-card-title class="subheading font-weight-bold">{{ category }} ({{num_videos}})</v-card-title>
          </v-flex>
          <v-flex v-for="video in videos" v-bind:key="video.id" xs12 md4>
            <NanumCard v-bind:video="video"/>
          </v-flex>
        </v-layout>
      </v-card>
    </v-container>
  </div>
</template>

<script>
import NanumCard from "./NanumCard";

export default {
  name: "Nanum",
  components: {
    NanumCard
  },
  data() {
    return {
      num_videos: 0
    };
  },
  props: ["category", "videos"],
  beforeUpdate() {
    this.num_videos = this.videos.length;
  }
};
</script>

<style>
</style>
