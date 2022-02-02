<template>
  <div id="app">
    {{disks}}
  </div>
</template>

<script>
import axios from "axios";
export default {
  name: "App",
  components: {},
  data() {
    return {
      disks: [],
    };
  },
  mounted() {
    axios
      .get("https://flynn.boolean.careers/exercises/api/array/music")
      .then((res) => {
        this.disks = res.data.response;
      });
  },
};
</script>

<style lang="scss">
</style>
