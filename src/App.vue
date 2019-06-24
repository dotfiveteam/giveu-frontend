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
          <v-btn flat to="/">오늘의 나눔</v-btn>
          <v-btn flat to="/nanum_king">나눔왕</v-btn>
        </v-toolbar-items>
      </v-toolbar>

      <v-content>
        <router-view/>
      </v-content>

      <v-footer app class="pa-3">
        <v-spacer></v-spacer>배너
      </v-footer>
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
