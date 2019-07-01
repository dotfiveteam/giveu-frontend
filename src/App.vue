<template>
  <div id="app">
    <v-app>
      <!-- <v-navigation-drawer app></v-navigation-drawer> -->

      <v-toolbar app dense>
        <v-toolbar-title>
          <h1>Give U</h1>
        </v-toolbar-title>
        <!-- <v-spacer></v-spacer>
        <v-toolbar-items>
          <v-btn flat to="/">오늘의 나눔</v-btn>
          <v-btn flat to="/nanum_king">나눔왕</v-btn>
        </v-toolbar-items>-->
      </v-toolbar>

      <v-content>
        <v-container text-xs-center fluid pa-0>
          <v-layout>
            <v-flex md2 hidden-sm-and-down>
              <v-card min-height="80vh" height="100%">
                <v-card-text>배너</v-card-text>
              </v-card>
            </v-flex>
            <v-flex xs12 md8>
              <router-view />
            </v-flex>
            <v-flex md2 hidden-sm-and-down>
              <v-card min-height="80vh" height="100%">
                <v-card-text>배너</v-card-text>
              </v-card>
            </v-flex>
          </v-layout>
        </v-container>
      </v-content>

      <!-- <v-footer app>
        <v-spacer></v-spacer>
        <v-flex xs12 text-xs-center>배너</v-flex>
      </v-footer>-->
    </v-app>
  </div>
</template>

<style>
* {
  box-sizing: border-box;
  margin: 0;
  padding: 0;
}
</style>
