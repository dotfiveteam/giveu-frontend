<template>
  <div>
    <v-container fluid grid-list-sm pa-0>
      <v-layout justify-center row wrap>
        <v-flex v-for="video in videos" v-bind:key="video.id" xs12 md4>
          <NanumCard v-bind:video="video" />
        </v-flex>
        <p class="pt-3" v-if="num_videos === 0">등록된 비디오가 없습니다.</p>
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
  props: ["videos"],
  beforeUpdate() {
    this.num_videos = this.videos.length;
  }
};
</script>

<style>
</style>
