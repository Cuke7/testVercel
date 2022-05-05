<template>
  <v-row justify="center">
    <v-col cols="12" lg="11" ref="col" class="pa-0">
      <div id="toto" :style="{ height: height + 'px' }" class="mt-4 mx-2">
        <v-row
          justify="space-around"
          class="mx-1"
          ref="row"
          :style="{ marginTop: space + 'px' }"
        >
          <v-col
            v-for="(pic, index) in pictures"
            :key="index"
            cols="12"
            md="4"
            class="pa-0"
            id="test"
          >
            <Picture :picture="pic" :index="index+1"></Picture>
          </v-col>
        </v-row>
      </div>
    </v-col>
  </v-row>
</template>

<script>
export default {
  data: () => ({
    pictures: [
      { info: "Merle noir - Turdus merula", id: "pic_2_mjk25k" },
      { info: "Rouge-gorge familier - Erithacus rubecula", id: "pic_3_xjxp11" },
      { info: "Mésange bleue - Cyanistes caeruleus", id: "pic_4_wxw2u5" },
      { info: "Mésange bleue - Cyanistes caeruleus", id: "pic_5_gvkwoe" },
      { info: "Mésange bleue - Cyanistes caeruleus", id: "pic_6_cqeg1b" },
      { info: "Mésange bleue - Cyanistes caeruleus", id: "pic_7_u6arhk" },
      { info: "Mésange bleue - Cyanistes caeruleus", id: "pic_33_fewvuk" },
      { info: "Mésange bleue - Cyanistes caeruleus", id: "pic_9_psjqmh" },
      { info: "Mésange bleue - Cyanistes caeruleus", id: "pic_8_dgiata" },
      { info: "Mésange bleue - Cyanistes caeruleus", id: "pic_10_soc2d3" },
      { info: "Mésange bleue - Cyanistes caeruleus", id: "pic_11_gtelvp" },
      { info: "Mésange charbonnière - Parus major", id: "pic_12_zhjapv" },
      { info: "Merle noir - Turdus merula", id: "pic_13_wtzbr6" },
      { info: "Merle noir - Turdus merula", id: "pic_14_sioyxv" },
      { info: "Merle noir - Turdus merula", id: "pic_16_crnxsd" },
      { info: "Merle noir - Turdus merula", id: "pic_15_g5nxlk" },
      {
        info: "Orite à longue queue - Aegithalos caudatus",
        id: "pic_17_srj8tv",
      },
      {
        info: "Orite à longue queue - Aegithalos caudatus",
        id: "pic_18_olpivs",
      },
      {
        info: "Orite à longue queue - Aegithalos caudatus",
        id: "pic_19_uuppz6",
      },
      { info: "Écureuil roux - Sciurus vulgaris", id: "pic_20_gx7vyg" },
      { info: "Écureuil roux - Sciurus vulgaris", id: "pic_21_twr8fy" },
      {
        info: "Orite à longue queue - Aegithalos caudatus",
        id: "pic_22_ja6aa4",
      },
      {
        info: "Orite à longue queue - Aegithalos caudatus",
        id: "pic_24_tpfrj6",
      },
      {
        info: "Orite à longue queue - Aegithalos caudatus",
        id: "pic_23_v31jia",
      },
      { info: "Mésange bleue - Cyanistes caeruleus", id: "pic_25_gff9bd" },
      { info: "Mésange bleue - Cyanistes caeruleus", id: "pic_26_okldyp" },
      {
        info: "Rouge-gorge familier - Erithacus rubecula",
        id: "pic_27_bw4nuu",
      },
      {
        info: "Rouge-gorge familier - Erithacus rubecula",
        id: "pic_28_qldjzy",
      },
      { info: "Mésange charbonnière - Parus major", id: "pic_29_rjhju7" },
      { info: "Merle noir - Turdus merula", id: "pic_31_mk9pqa" },
      { info: "Merle noir - Turdus merula", id: "pic_30_x3aovk" },
      { info: "Merle noir - Turdus merula", id: "pic_32_ovzkcm" },
      { info: "Corneille noire - Corvus corone", id: "pic_34_pakqck" },
      {
        info: "Troglodyte mignon - Troglodytes troglodytes",
        id: "pic_35_kr268b",
      },
      { info: "Étourneau sansonnet - Sturnus vulgaris", id: "pic_36_f0dq9x" },
      { info: "Étourneau sansonnet - Sturnus vulgaris", id: "pic_37_lszsx1" },
      {
        info: "Fauvette à tête noire - Sylvia atricapilla",
        id: "pic_38_l0nmtb",
      },
      { info: "Merle noir - Turdus merula", id: "pic_39_hqbx2y" },
      {
        info: "Orite à longue queue - Aegithalos caudatus",
        id: "pic_40_kftueq",
      },
      { info: "Abeille - Anthophila", id: "pic_41_bwk1tr" },
      { info: "Abeille - Anthophila", id: "pic_42_svskbm" },
    ],
    height: 200,
    space: 20,
  }),
  computed: {
    // heigh() {
    //   return window.innerHeight - 100;
    // },
  },
  methods: {
    getUrl(index) {
      let url = "/pictures/pic_" + index + ".jpg";
      return url;
    },
    resizeUI() {
      let height = document.querySelector(".v-main").clientHeight - 140;
      let space = Math.floor(((this.$refs.row.clientWidth / 3) * 0.05 * 2) / 3);

      this.height = height;
      this.space = space;
    },
  },
  mounted() {
    this.resizeUI();
    //this.$refs.musicPlayer.load_playlist({ name: "Guitars", url: "https://www.youtube.com/playlist?list=PLY80CRqvcxEXtmbMSJDqIK4uk_FB3j5I8" });
  },
};
</script>

<style scoped>
#toto {
  overflow-y: scroll;
}

#test {
  margin-top: 16px;
}

/* width */
::-webkit-scrollbar {
  width: 5px;
}

/* Track */
::-webkit-scrollbar-track {
  box-shadow: inset 0 0 5px rgba(128, 128, 128, 0);
  border-radius: 10px;
}

/* Handle */
::-webkit-scrollbar-thumb {
  background: rgb(255, 255, 255);
  border-radius: 5px;
}

/* Handle on hover */
::-webkit-scrollbar-thumb:hover {
  background: #b8b8b8;
}
</style>
