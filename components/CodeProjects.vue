<template>
  <v-row align="center" justify="center">
    <v-col cols="10" md="8">
      <v-row align="center">
        <v-col cols="auto">
          <div class="text-h2">
            {{ projectData.titre }}
          </div>
        </v-col>
      </v-row>

      <div class="text-body-1 mt-12" v-html="projectData.descriptionHtml"></div>

      <div class="text-md-left text-center">
        <v-btn
          color="primary"
          class="mt-6"
          :href="projectData.url"
          target="_blank"
        >
          {{ projectData.titre }}
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
    }
  }
};
</script>
