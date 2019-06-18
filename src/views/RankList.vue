<template>
  <div>
    <ol>
      <div v-for="channel in rank_list" v-bind:key="channel.id">
        <v-btn outline block v-on:click="GoToChannel(channel.id)">
          <li>{{channel.name}}</li>
        </v-btn>
      </div>
    </ol>
  </div>
</template>

<script>
import rank_list from "../assets/rank_list.json";

export default {
  name: "RankList",
  data() {
    return {
      rank_list: rank_list
    };
  },
  methods: {
    GoToChannel(channel_id) {
      window.location.href = "https://www.youtube.com/channel/" + channel_id;
    }
  }
};
</script>

<style>
</style>
