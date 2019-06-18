<template>
  <div>
    <v-card>
      <div v-for="youtube_channel in youtube_list" v-bind:key="youtube_channel.id">
        <Events v-bind:channel_name="youtube_channel.name" v-bind:videos="youtube_channel.videos"/>
      </div>
    </v-card>
  </div>
</template>

<script>
import Events from "../components/Events";

export default {
  name: "Home",
  components: {
    Events
  },
  data() {
    return {
      youtube_list: null
    };
  },
  mounted() {
    this.axios
      .get("http://stolenbyte.kr:8081/api/v1/youtube/")
      .then(response => {
        this.youtube_list = response.data;
      });
  }
};
</script>

<style>
</style>
