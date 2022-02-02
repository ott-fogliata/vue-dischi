<template>
  <header>
    <select 
      v-model="select"
      @change="$emit('search', select)">
      <option value="all">All</option>
      <option v-for="(genre, i) in list" :key="i" :value="genre">{{genre}}</option>
    </select>
  </header>
</template>

<script>
export default {
  props: {
    list: Array
  },
  data() {
    return {
      select: 'all',
    }
  }
};
</script>

<style lang="scss" scoped>
@import "@/style/headerStyle.scss";
</style>
