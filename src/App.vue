<template>
  <div id="app">
    <main-container :disks="filteredDisc"/>
    <button @click="filterDisc('Pop')">filtra</button>
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
      filteredDisc: []
    };
  },
  mounted() {
    axios
      .get("https://flynn.boolean.careers/exercises/api/array/music")
      .then((res) => {
        this.disks = res.data.response;
        this.filteredDisc = res.data.response;
      });
  },
  methods: {
    filterDisc(genre) {
      this.filteredDisc = this.disks.filter((disc) => {
        return disc.genre === genre;
      })
    }
  }
};
</script>

<style lang="scss">
*{
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}
</style>
