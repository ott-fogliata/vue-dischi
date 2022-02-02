<template>
  <div id="app">
    <main-container :disks="disks"/>
  </div>
</template>

<script>
import axios from "axios";
import MainContainer from './components/MainContainer.vue'

export default {
  name: "App",
  components: {
    MainContainer,
  },
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
*{
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}
</style>
