<template>
  <div>
    <Events v-bind:events="video_list_tmp['(MUTUBE)와꾸대장봉준']"/>
  </div>
</template>

<script>
import Events from "../components/Events";
import video_list_tmp from "../assets/video_list_tmp.json";

export default {
  name: "Home",
  components: {
    Events
  },
  data() {
    return {
      video_list_tmp: video_list_tmp
      // events: [
      //   {
      //     id: 1,
      //     date: "2019-07-02",
      //     finished: false,
      //     videoId: "2-HAkAmdOAA"
      //   },
      //   {
      //     id: 2,
      //     date: "2019-03-23",
      //     finished: true,
      //     videoId: "a2GujJZfXpg"
      //   },
      //   {
      //     id: 3,
      //     date: "2019-02-12",
      //     finished: true,
      //     videoId: "L1BDM1oBRJ8"
      //   }
      // ]
    };
  }
};
</script>

<style>
</style>
