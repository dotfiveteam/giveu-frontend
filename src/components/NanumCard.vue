<template>
  <div>
    <v-flex xs12>
      <v-card>
        <v-img v-bind:src="thumbnail">
          <v-layout pa-2 column fill-height class="white--text">
            <v-flex shrink>
              <v-card-title class="pa-0 text-outline">
                <h2>{{channel}}</h2>
              </v-card-title>
            </v-flex>
            <v-card-text class="text-outline">{{title}}</v-card-text>
            <v-card-text class="pa-0 text-xs-right text-outline">
              <h3>나눔: {{reward}}</h3>
            </v-card-text>
            <v-spacer></v-spacer>
            <v-card-text class="pa-0 text-xs-right caption font-weight-thin text-outline">
              등록일: {{published_date}}
              <br>
              만료일: {{end_date}}
            </v-card-text>
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
  name: "NanumCard",
  props: ["video"],
  data() {
    return {
      channel: this.video.channel,
      title: this.video.title,
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
    GoToVideo() {
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
