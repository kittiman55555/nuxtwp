<template>
  <v-container grid-list-md text-center>
    <v-layout wrap>
      <v-flex xs8>
        <h1>NEW POST</h1>
        <v-flex xs4 blog-post v-for="post in data" :key="post.id">
          <v-card class="mx-auto" max-width="400">
            <v-img
              class="white--text"
              height="200px"
              :src='post.better_featured_image.source_url'
            >
              <v-card-title class="align-end fill-height" v-html="post.title.rendered"></v-card-title>
            </v-img>
            <v-card-text>
              <span v-html="post.excerpt.rendered"></span>
            </v-card-text>
            <v-card-actions>
              <v-btn text color="primary">readmore</v-btn>
              <v-btn text color="orange">share</v-btn>
            </v-card-actions>
          </v-card>
        </v-flex>
      </v-flex>
      <v-flex xs4>
        <h1>HOT POST</h1>
      </v-flex>
    </v-layout>
  </v-container>
</template>





<script>
import Logo from "~/components/Logo.vue";
import VuetifyLogo from "~/components/VuetifyLogo.vue";
import axios from "axios";

export default {
  asyncData({ params, error }) {
    return axios
      .get("http://pawathemes.com/demo8/restwp/wp-json/wp/v2/posts")
      .then(res => {
        return { data: res.data };
      })
      .catch(e => {
        error({ statusCode: 404, message: "Post not found" });
      });
  }
};
</script>





<style>
.blog-post {
    float: left;
}
.v-card__title {
    align-items: flex-end;
    color: #000;
}
.theme--light.v-card {
    margin: 20px;
}
.v-application .secondary {
    background-color: #5cbbf6 !important;
    border-color: #5cbbf6 !important;
}
</style>