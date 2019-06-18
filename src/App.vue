<template>
  <div id="app">
    <v-app>
      <!-- <v-navigation-drawer app></v-navigation-drawer> -->

      <v-toolbar app>
        <v-toolbar-title>
          <h1>Give U</h1>
        </v-toolbar-title>
        <v-spacer></v-spacer>
        <v-toolbar-items class>
          <v-btn flat to="/">이벤트</v-btn>
          <v-btn flat to="/rank_list">랭크리스트</v-btn>
          <!-- <v-btn flat to="/about">About</v-btn> -->
        </v-toolbar-items>
      </v-toolbar>

      <v-content>
        <router-view/>
      </v-content>

      <v-footer app>give me</v-footer>
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
