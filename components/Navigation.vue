<template>
  <div>
    <v-app id="inspire">
      <div>
        <v-toolbar>
          <v-toolbar-title>BLOG NUXTWP</v-toolbar-title>
          <div class="flex-grow-1"></div>
          <v-toolbar-items>
            <v-btn text to="/">Home</v-btn>
            <v-btn text to="/about">About</v-btn>
            <v-btn text to="/contact">Contact</v-btn>
          </v-toolbar-items>
        </v-toolbar>
      </div>
    </v-app>
  </div>
</template>


<style>
.v-application--wrap{
  min-height: auto;
}
</style>