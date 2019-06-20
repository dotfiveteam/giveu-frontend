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
          <v-btn flat to="/about">About</v-btn>
        </v-toolbar-items>
      </v-toolbar>

      <v-content>
        <router-view/>
      </v-content>

      <v-footer app class="pa-3">
        <v-spacer></v-spacer>여기 footer인데, 배너광고 ㄱㄱ?
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
