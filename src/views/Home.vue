<template>
  <v-content>
    <Hero />
    <Gallery />
    <LatestPost />
  </v-content>
</template>

<script>
import Hero from "../components/Hero.vue";
import Gallery from "../components/Gallery.vue";
import LatestPost from "../components/LatestPost.vue";
export default {
  name: "Home",
  components: {
    Hero,
    Gallery,
    LatestPost,
  },
  data() {
    return {
      items: [],
    };
  },
};
</script>
