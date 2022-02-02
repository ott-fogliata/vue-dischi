<template>
  <header>
    <select 
      v-model="select"
      @change="$emit('search', select)">
      <option value="all">All</option>
      <option value="rock">Rock</option>
      <option value="pop">Pop</option>
      <option value="jazz">Jazz</option>
      <option value="metal">Metal</option>
    </select>
  </header>
</template>

<script>
export default {
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
