<template>
  <v-container>
    <v-footer padless>
      <v-card flat tile class="black--text text-center">
        <v-card-text>
          <v-btn
            v-for="icon in icons"
            :key="icon"
            class="mx-4 black--text"
            icon
          >
            <v-icon size="24px">
              {{ icon }}
            </v-icon>
          </v-btn>
        </v-card-text>

        <v-card-text class="black--text pt-0">
          “The best images are the ones that retain their strength and impact
          over the years, regardless of the number of times they are viewed.” –
          Anne Geddes
        </v-card-text>

        <v-divider></v-divider>

        <v-card-text class="black--text">
          {{ new Date().getFullYear() }} —
          <strong>Photography by Bittersweet</strong>
        </v-card-text>
      </v-card>
    </v-footer>
  </v-container>
</template>

<script>
export default {
  name: "Footer",
  data: () => ({
    icons: ["mdi-facebook", "mdi-twitter", "mdi-linkedin", "mdi-instagram"],
  }),
};
</script>
