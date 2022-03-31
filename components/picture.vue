<template>
  <v-dialog v-model="dialog" max-width="1000">
    <template v-slot:activator="{ on, attrs }">
      <div class="text-center" v-bind="attrs" v-on="on">
        <nuxt-img :src="getUrl(index)" width="500" provider="static">
        </nuxt-img>
      </div>
    </template>

    <v-img :src="getUrl(index)" class="white--text align-end">
      <div color="rgb(255,255,255,0.5)">
        <v-card-title>
          <span style="background-color: #252523" class="px-2">
            {{ picture.info }}</span
          ></v-card-title
        >
      </div>
    </v-img>
  </v-dialog>
</template>

<script>
export default {
  props: ["picture", "index"],
  data: () => ({
    dialog: false,
  }),
  methods: {
    getUrl(index) {
      let url = "/pictures/pic_" + index + ".jpg";
      return url;
    },
    formatUrl(id) {
      return (
        "https://res.cloudinary.com/louiscassany/image/upload/v1648648964/Birds/" +
        id +
        ".webp"
      );
    },
  },
};
</script>

<style scoped>
img {
  width: 95%;
}

.customDialog {
  width: 50vw;
}
</style>
