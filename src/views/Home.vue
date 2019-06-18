<template>
  <div>
    <Events v-bind:events="events"/>
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
      events: [
        {
          id: 1,
          date: "2019-07-02",
          finished: false,
          videoId: "2-HAkAmdOAA"
        },
        {
          id: 2,
          date: "2019-03-23",
          finished: true,
          videoId: "a2GujJZfXpg"
        },
        {
          id: 3,
          date: "2019-02-12",
          finished: true,
          videoId: "L1BDM1oBRJ8"
        }
      ]
    };
  }
};
</script>

<style>
</style>
