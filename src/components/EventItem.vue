<template>
  <div>
    <v-flex xs12>
      <v-card v-bind:dark="event.finished">
        <v-card-title>
          <div class="headline">
            <h3>{{title}}</h3>
          </div>
        </v-card-title>
        <p class="text-xs-right">{{event.date}} 까지</p>
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
  props: ["event"],
  data() {
    return {
      title: "유툽API - 제목 끌어오기",
      thumbnail: "https://img.youtube.com/vi/" + this.event.videoId + "/0.jpg"
    };
  },
  methods: {
    GoToVideo() {
      window.location.href =
        "https://www.youtube.com/watch?v=" + this.event.videoId;
    }
  }
};
</script>

<style scoped>
</style>
