<template>
  <div>
    <v-card>
      <h1>나눔왕 랭킹</h1>
      <v-container fluid grid-list-lg>
        <v-layout justify-center row wrap>
          <v-layout row wrap>
            <v-flex v-for="(channel, index)  in channels" v-bind:key="channel.id" xs12>
              <v-card>
                <v-layout row wrap>
                  <v-flex xs1>
                    <v-card-title class="pa-0" justify-center>
                      <h2>{{index}}</h2>
                    </v-card-title>
                  </v-flex>
                  <v-flex xs3>
                    <v-card-text class="pa-0">{{channel.name}}</v-card-text>
                  </v-flex>
                  <v-flex xs8>
                    <v-card-text class="pa-0">{{channel.desc}}</v-card-text>
                    <v-card-text class="pa-0">누적 기부금액: {{channel.net_donation.toLocaleString()}}원</v-card-text>
                  </v-flex>
                </v-layout>
              </v-card>
            </v-flex>
          </v-layout>
        </v-layout>
      </v-container>
    </v-card>
  </div>
</template>

<script>
export default {
  name: "NanumKing",
  data() {
    return {
      channels: []
    };
  },
  mounted() {
    for (let i = 0; i < 5; i++) {
      let new_channel = {
        id: i,
        name: "채널" + Math.floor(Math.random() * 100),
        desc: "테스트용으로 만든 가상 유투브 채널 입니다.",
        net_donation: Math.floor(Math.random() * 100) * 1000
      };
      this.channels.push(new_channel);
    }
    // sort videos
    this.channels.sort(function(a, b) {
      return a.net_donation < b.net_donation
        ? 1
        : a.net_donation > b.net_donation
        ? -1
        : 0;
    });
  }
};
</script>

<style>
</style>
