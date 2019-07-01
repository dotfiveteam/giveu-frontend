<template>
  <div>
    <v-flex xs12 class="pb-2">
      <v-btn-toggle mandatory v-model="nanum_toggle_exclusive">
        <v-btn flat>신규</v-btn>
        <v-btn flat>진행중</v-btn>
        <v-btn flat>나눔왕</v-btn>
      </v-btn-toggle>
    </v-flex>
    <Nanum v-if="nanum_toggle_exclusive === 0" v-bind:videos="newly_added_list" />
    <Nanum v-if="nanum_toggle_exclusive === 1" v-bind:videos="date_sorted_list" />
    <NanumKing v-if="nanum_toggle_exclusive === 2" />
  </div>
</template>

<script>
import Nanum from "../components/Nanum";
import NanumKing from "../components/NanumKing";

export default {
  name: "Home",
  components: {
    Nanum,
    NanumKing
  },
  data() {
    return {
      nanum_toggle_exclusive: 1,
      num_days_recent: 2,
      channel_list: [],
      date_sorted_list: [],
      newly_added_list: [],
      ending_soon_list: []
    };
  },
  mounted() {
    // get the list from API server -> channel_list
    // sort videos in the order of published date -> date_sorted_list
    // extract newly added (past 7 days) videos -> newly_added_list
    this.axios
      .get("http://stolenbyte.kr:8081/api/v1/youtube/")
      .then(response => {
        this.channel_list = response.data;
        // list all videos into a new array
        let video_list = [];
        for (let i = 0; i < this.channel_list.length; i++) {
          for (let j = 0; j < this.channel_list[i].videos.length; j++) {
            let new_video = this.channel_list[i].videos[j];
            new_video["channel"] = this.channel_list[i].name;
            video_list.push(new_video);
          }
        }
        // sort videos
        video_list.sort(function(a, b) {
          return a.published_at < b.published_at
            ? 1
            : a.published_at > b.published_at
            ? -1
            : 0;
        });
        this.date_sorted_list = video_list;
        // extract newly added
        let today = new Date();
        today.setDate(today.getDate() - this.num_days_recent);
        // today = today.toJSON().slice(0, 10).replace(/-/g, "-");
        today = today
          .toISOString()
          .substring(0, 10)
          .replace(/-/g, "-");
        for (let i = 0; i < this.date_sorted_list.length; i++) {
          if (this.date_sorted_list[i].published_at > today) {
            this.newly_added_list.push(this.date_sorted_list[i]);
          }
        }
      });
  },
  methods: {}
};
</script>

<style>
</style>
