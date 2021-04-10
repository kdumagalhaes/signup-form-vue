<template>
    <div class="left-content">
        <MainCTA />
    </div>
</template>

<script>
// molecules
import { MainCTA } from '@/components/molecules'

export default {
    components: {
        MainCTA,
    },
}
</script>

<style lang="scss" scoped>
.left-content {
    height: 100vh;
    width: 50%;
    display: flex;
    justify-content: flex-end;
    align-items: center;
}
</style>
