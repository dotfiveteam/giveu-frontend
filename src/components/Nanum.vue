<template>
  <div>
    <v-container fluid grid-list-lg>
      <v-layout justify-center row wrap>
        <v-expansion-panel>
          <v-expansion-panel-content>
            <template v-slot:header>
              <div class="subheading font-weight-bold">{{ category }}</div>
            </template>
            <v-layout row wrap>
              <v-flex v-for="video in videos" v-bind:key="video.id" xs12 md4>
                <NanumCard v-bind:video="video"/>
              </v-flex>
            </v-layout>
          </v-expansion-panel-content>
        </v-expansion-panel>
      </v-layout>
    </v-container>
  </div>
</template>

<script>
import NanumCard from "./NanumCard";

export default {
  name: "Nanum",
  components: {
    NanumCard
  },
  props: ["category", "videos"]
};
</script>

<style>
</style>
