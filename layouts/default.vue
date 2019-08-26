<template>
  <v-content>
    <Navigation />
    <v-container>
      <nuxt />
    </v-container>
  </v-content>
</template>

<script>
import Navigation from "~/components/Navigation.vue";

export default {
  components: {
    Navigation
  }
};
</script>
