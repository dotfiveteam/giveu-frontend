<template>
  <div>
    <v-flex xs12>
      <v-card class="mb-1">
        <v-layout pa-2 column>
          <v-layout row wrap pa-2>
            <v-flex xs4>
              <v-avatar size="100%" v-on:click="goToVideo">
                <v-img v-bind:src="thumbnail"></v-img>
              </v-avatar>
            </v-flex>
            <v-flex xs8>
              <v-card-title class="pa-0">
                <h3 fill-height>{{video_title}}</h3>
              </v-card-title>
              <v-spacer></v-spacer>
              <v-card-text class="pa-0 text-xs-right">{{channel_name}}</v-card-text>
              <v-card-text class="pa-0 text-xs-right">나눔품: {{reward}}</v-card-text>
              <v-card-text
                class="pa-0 text-xs-right caption font-weight-thin"
              >등록일: {{published_date}} | 만료일: {{end_date}}</v-card-text>
            </v-flex>
          </v-layout>
        </v-layout>
      </v-card>
    </v-flex>
  </div>
</template>

<script>
export default {
  name: "NanumCard",
  props: ["video"],
  data() {
    return {
      channel_name: this.video.channel,
      video_title: this.video.title,
      reward: "몰라", // 하드코딩됨! ------------------------------------------------------------------------------------------------------
      thumbnail: this.video.thumbnail, //"https://img.youtube.com/vi/" + this.video.video_id + "/0.jpg",
      link: "https://www.youtube.com/watch?v=" + this.video.video_id,
      published_date: new Date(this.video.published_at)
        .toISOString()
        .substring(0, 10),
      end_date: "몰라" //new Date().toISOString().sub~string(0, 10) // 하드코딩됨! ----------------------------------------------------------------
    };
  },
  methods: {
    goToVideo() {
      window.location.href = this.link;
    }
  }
};
</script>

<style scoped>
.text-outline {
  text-shadow: -1px -1px 0 #000, 1px -1px 0 #000, -1px 1px 0 #000,
    1px 1px 0 #000;
}
</style>
