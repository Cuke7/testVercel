<template>
  <v-app>
    <v-app-bar app color="transparent">
      <v-row class="pl-12">
        <v-col cols="auto">
          <nuxtLink to="/" class="white--text"> Photos </nuxtLink>
        </v-col>
        <v-col cols="auto" class="ml-12">
          <nuxtLink to="/apps" class="white--text"> Applications </nuxtLink>
        </v-col>
      </v-row>
    </v-app-bar>
    <v-main>
      <v-container fluid>
        <Nuxt />
      </v-container>
    </v-main>
    <v-footer app> Louis CASSANY </v-footer>
  </v-app>
</template>

<script>
export default {
  //
};
</script>

<style>
.v-main {
  background-image: linear-gradient(
    to bottom,
    #243aa3,
    #004f9a,
    #005064,
    #004928,
    #2b3f00
  );
}

a {
  /* text-decoration: none; */
}
</style>
