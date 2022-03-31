<template>
  <v-row align="center" justify="center">
    <v-col order="2" :order-md="order1" cols="10" md="4" lg="4">
      <v-img
        contain
        max-width="400"
        :src="projectData.mockup_url"
        class="mx-auto"
      ></v-img>
    </v-col>
    <v-col order="1" :order-md="order2" cols="10" md="6" lg="4">
      <v-row align="center">
        <v-col cols="auto">
          <div class="text-h4" v-if="this.$vuetify.breakpoint.mobile">
            {{ projectData.titre }}
          </div>
          <div class="text-h2" v-else>
            {{ projectData.titre }}
          </div>
        </v-col>
        <v-col cols="auto">
          <v-avatar size="50" v-if="this.$vuetify.breakpoint.mobile">
            <v-img :src="projectData.icon_url"></v-img>
          </v-avatar>
          <v-avatar size="70" v-else>
            <v-img :src="projectData.icon_url"></v-img>
          </v-avatar>
        </v-col>
      </v-row>

      <div
        class="text-body-1 mt-12 text-justify"
        v-html="projectData.description"
      ></div>

      <div class="text-md-left text-center">
        <v-btn
          color="primary"
          class="mt-6"
          :href="projectData.url"
          target="_blank"
        >
          Essayer {{ projectData.titre }}
        </v-btn>
      </div>
    </v-col>
  </v-row>
</template>

<script>
export default {
  props: ["projectData", "index"],
  computed: {
    order1() {
      return (this.index % 2) + 1;
    },
    order2() {
      if (this.order1 == 1) {
        return 2;
      } else {
        return 1;
      }
    },
  },
};
</script>
