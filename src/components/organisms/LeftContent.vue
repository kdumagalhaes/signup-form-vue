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

@media only screen and (max-width: $mobile) {
    .left-content {
        width: 100%;
        height: 100%;
        margin: 80px 0;
        text-align: center;
    }
}
</style>
