<template>
  <div>
    <v-container fluid grid-list-lg>
      <v-layout justify-center row wrap>
        <v-expansion-panel>
          <v-expansion-panel-content>
            <template v-slot:header>
              <div class="subheading font-weight-bold">{{ category }} ({{num_videos}})</div>
            </template>
            <v-layout row wrap>
              <v-flex v-for="video in videos" v-bind:key="video.id" xs12 md4>
                <NanumCard v-bind:video="video"/>
              </v-flex>
              <v-flex v-if="num_videos == 0">
                <v-flex xs12 text-xs-center>등록된 비디오가 없습니다</v-flex>
              </v-flex>
            </v-layout>
          </v-expansion-panel-content>
        </v-expansion-panel>
      </v-layout>
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
  updated() {
    this.num_videos = this.videos.length;
  }
};
</script>

<style>
</style>
