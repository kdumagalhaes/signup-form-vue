<template>
    <div class="main-cta">
        <MainCTAText text="Learn to code by watching others" />
        <MainCTAParagraph
            text="See how experienced developers solve problems in real-time. Watching scripted tutorials is great, but understanding how developers think is invaluable."
        />
    </div>
</template>

<script>
// atoms
import { MainCTAText, MainCTAParagraph } from '@/components/atoms'

export default {
    components: {
        MainCTAParagraph,
        MainCTAText,
    },
}
</script>

<style lang="scss" scoped>
.main-cta {
    width: 100%;
    max-width: 500px;
}
</style>
