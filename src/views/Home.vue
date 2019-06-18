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
    };
  }
};
</script>

<style>
</style>
