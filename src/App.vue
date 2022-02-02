<template>
  <div id="app">
    <header-box @search="filterDisc" :list="genreList"/>
    <main-container :disks="filteredDisc" />
    {{ userName }}
  </div>
</template>

<script>
import axios from "axios";
import MainContainer from "./components/MainContainer.vue";
import HeaderBox from "./components/HeaderBox.vue";

export default {
  name: "App",
  components: {
    MainContainer,
    HeaderBox,
  },
  data() {
    return {
      disks: [],
      filteredDisc: [],
      user: {
        name: 'Gino',
        surname: 'Paoli'
      }
    };
  },
  computed: {
    userName() {
      return `${this.user.name} ${this.user.surname}`
    },
    genreList() {
      const list = [];
      this.disks.forEach((element) => {
        if(!list.includes(element.genre.toLowerCase())) {
          list.push(element.genre.toLowerCase())
        }
      })
      return list;
    }
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
        return disc.genre.toLowerCase() === genre || genre === 'all';
      });
    },
  },
};
</script>

<style lang="scss">
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}
</style>
