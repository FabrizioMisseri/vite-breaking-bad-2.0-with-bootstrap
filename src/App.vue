<script>
import { store } from '../store.js';
import axios from "axios";
import appHeader from './components/appHeader.vue';
import appMain from './components/appMain.vue';
import appLoader from './components/appLoader.vue';

export default {
  name: "app vue",

  components: {
    appHeader,
    appMain,
    appLoader,
  },

  data() {
    return {
      store,
    }
  },

  created() {
    this.callToAxios(this.store.category);
  },

  methods: {
    callToAxios(category) {
      if (category === "") {

        this.store.flagLoading = false;

        axios
          .get("https://www.breakingbadapi.com/api/characters")
          .then((resp) => {
            this.store.personaggi = resp.data;
          });

      } else if (category === "Breaking Bad") {
        axios
          .get("https://www.breakingbadapi.com/api/characters?category=Breaking+Bad")
          .then((resp) => {
            this.store.personaggi = resp.data;
          });
      } else {
        axios
          .get("https://www.breakingbadapi.com/api/characters?category=Better+Call+Saul")
          .then((resp) => {
            this.store.personaggi = resp.data;
          });
      }

      this.store.flagLoading = true;
    }

  }

}
</script>

<template>
  <appHeader @event="callToAxios(this.store.category)" />
  <appMain v-if="store.flagLoading" />
  <appLoader v-else />
</template>

<style lang="scss">
@use "./style.scss" as *;
</style>
