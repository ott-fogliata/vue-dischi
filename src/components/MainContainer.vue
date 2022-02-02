<template>
    <div>
        <disc-card title="NEW JERSEY" image="https://th.bing.com/th?id=OIF.A1J2Vq9cZDM%2fopfAA9jFKA&pid=ImgDet&rs=1" author="Gino" date="1980"/>
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

</style>