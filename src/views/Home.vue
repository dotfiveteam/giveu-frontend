<template>
  <div>
    <v-card>
      <Nanum category="새로 등록된 나눔" v-bind:videos="newly_added_list"/>
      <Nanum category="곧 끝날 나눔" v-bind:videos="ending_soon_list"/>
      <Nanum category="진행중인 나눔" v-bind:videos="date_sorted_list"/>
    </v-card>
  </div>
</template>

<script>
import Nanum from "../components/Nanum";

export default {
  name: "Home",
  components: {
    Nanum
  },
  data() {
    return {
      num_days_recent: 7,
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
        for (let i = 0; i < this.channel_list.length; i++) {
          for (let j = 0; j < this.channel_list[i].videos.length; j++) {
            let new_video = this.channel_list[i].videos[j];
            new_video["channel"] = this.channel_list[i].name;
            this.date_sorted_list.push(new_video);
          }
        }
        // sort videos
        this.date_sorted_list.sort(function(a, b) {
          return new Date(a.published_at) < new Date(b.published_at);
        });
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
  }
};
</script>

<style>
</style>
