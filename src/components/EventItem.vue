<template>
  <div>
    <v-flex xs12>
      <v-card width="50vh" v-bind:dark="video.finished">
        <v-card-title>
          <div class="headline">
            <h5>{{title}}</h5>
          </div>
        </v-card-title>
        <p class="ma-0 pa-0 text-xs-right">게시일: {{published_date}}</p>
        <v-img v-bind:src="thumbnail"></v-img>
        <v-card-actions>
          <v-btn outline block v-on:click="GoToVideo">구독, 좋아요, 댓글달기 ㄱㄱ</v-btn>
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
