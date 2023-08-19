<template>
  <div class="block LatestPostBlock">
    <v-container>
      <h2 class="text-center">Latest Post</h2>
      <v-row>
        <v-col cols="12" md="4" v-for="item in items" :key="item.id">
          <v-card outlined class="mx-auto">
            <v-img class="white--text align-end" height="200px" :src="item.src">
              <v-card-title>{{ item.title }}</v-card-title>
            </v-img>

            <v-card-subtitle class="pb-0">{{ item.subtitle }}</v-card-subtitle>

            <v-card-text class="text--primary">
              <div>{{ item.description }}</div>
            </v-card-text>

            <v-card-actions>
              <v-btn color="primary" text> More </v-btn>
            </v-card-actions>
          </v-card>
        </v-col>
      </v-row>
    </v-container>
  </div>
</template>

<script>
export default {
  name: "LatestPost",
  data() {
    return {
      items: [
        {
          id: 1,
          title: "Classic never gets old",
          subtitle: "1001 ways of music",
          description:
            "Embark on a journey of musical old classics, with beautiful and historic tunes. An unforgettable musical journey.",
          src: require("../assets/images/kmg3.jpg"),
        },
        {
          id: 2,
          title: "A meaningful silent night",
          subtitle: "1,000 miles of wonder",
          description:
            "Detach yourself from reality and immerse yourself in a night world of imagination. Discover new stories, emotions and adventures.",
          src: require("../assets/images/kmg4.jpg"),
        },
        {
          id: 3,
          title: "Flower of beauty",
          subtitle: "3,000 happiness of life",
          description:
            "Spread joy and cheer this holiday season with beautiful flower gardens, warm gatherings, and meaningful gifts.",
          src: require("../assets/images/kmg5.jpg"),
        },
      ],
    };
  },
};
</script>
