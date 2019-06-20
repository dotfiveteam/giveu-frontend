<template>
  <div>
    <v-flex xs12>
      <v-card v-bind:dark="video.finished">
        <v-img v-bind:src="thumbnail">
          <v-layout pa-2 column fill-height class="white--text">
            <v-flex shrink>
              <v-card-title class="ma-0 pa-0">{{title}}</v-card-title>
            </v-flex>
            <v-spacer></v-spacer>
            <v-card-text class="ma-0 pa-0 text-xs-right caption font-weight-thin">{{published_date}}</v-card-text>
          </v-layout>
        </v-img>
        <v-card-actions>
          <v-btn outline block v-on:click="GoToVideo">ㄱㄱ</v-btn>
        </v-card-actions>
      </v-card>
    </v-flex>
  </div>
</template>

<script>
export default {
  name: "EventItem",
  props: ["video"],
  data() {
    return {
      title: this.video.title,
      thumbnail: this.video.thumbnail, //"https://img.youtube.com/vi/" + this.video.video_id + "/0.jpg",
      link: "https://www.youtube.com/watch?v=" + this.video.video_id,
      published_date: new Date(this.video.published_at)
        .toISOString()
        .substring(0, 10)
    };
  },
  methods: {
    GoToVideo() {
      window.location.href = this.link;
    }
  }
};
</script>

<style scoped>
</style>
