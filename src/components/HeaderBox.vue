<template>
  <header>
    <button @click="$emit('search', 'Rock')">Filter Button</button>
  </header>
</template>

<script>
export default {};
</script>

<style lang="scss" scoped>
@import "@/style/headerStyle.scss";
</style>
