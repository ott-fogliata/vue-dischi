<template>
    <div class="container-main">
        <disc-card v-for="(disk, index) in disks" :key="index" :image="disk.poster" :author="disk.author" :title="disk.title" :date="disk.year" />
    </div>
</template>

<script>
import DiscCard from './DiscCard.vue'

export default {
    components: {
        DiscCard,
    },
    props:{
        disks: Array,
    }
}
</script>

<style lang="scss" scoped>
.container-main{
    display: flex;
    flex-wrap: wrap;
    width: 1200px;
    margin: 0 auto;
}
</style>