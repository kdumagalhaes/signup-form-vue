<template>
    <main class="main-template">
        <LeftContent />
        <RightContent />
    </main>
</template>

<script>
// organisms
import { LeftContent, RightContent } from '@/components/organisms'

export default {
    components: {
        LeftContent,
        RightContent,
    },
}
</script>

<style lang="scss" scoped>
.main-template {
    width: 100%;
    display: flex;
    justify-content: space-between;
    align-items: center;
}

@media only screen and (max-width: $mobile) {
    .main-template {
        flex-direction: column;
    }
}
</style>
