<template>
  <div id="app">
    <v-header :seller="seller"></v-header>
    <div>
      <tab></tab>
    </div>
  </div>
</template>

<script>
import { getSeller } from "./api";
import VHeader from "components/v-header/v-header";
import Tab from "components/tab/tab";

export default {
  name: "App",
  data() {
    return {
      seller: {},
    };
  },
  created() {
    this._getSeller();
  },
  methods: {
    _getSeller() {
      getSeller().then((seller) => {
        this.seller = seller;
      });
    },
  },
  components: {
    VHeader,
    Tab,
  },
};
</script>

<style lang="scss">
</style>
