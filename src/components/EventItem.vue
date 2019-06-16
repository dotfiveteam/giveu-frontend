<template>
  <div class="event-item" v-bind:class="{'is-finished':event.finished}">
    <h2>{{title}}</h2>
    <p class="event-date">{{event.date}} 까지</p>
    <img v-bind:src="thumbnail" alt="thumbnail">
    <p class="event-todo">
      구독, 좋아요, 댓글달기
      <button type="button" v-on:click="GoToVideo">ㄱㄱ</button>
    </p>
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
.event-item {
  border: 1px solid black;
  padding: 10px;
  margin: 10px;
}

h2 {
  text-align: center;
}

.event-date {
  text-align: right;
  font-size: 0.5rem;
}

.is-finished {
  background: gray;
  color: white;
}

img {
  height: 100%;
  width: 100%;
}

button {
  border: 1px solid black;
  background: none;
  box-shadow: none;
  padding: 5px;
  border-radius: 10px;
}

.event-todo {
  text-align: right;
}
</style>
