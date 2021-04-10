<template>
    <div class="right-content">
        <PromoCTA strong="Try it free 7 days " text="then $20/mo. thereafter" />
        <FreeTrialForm />
    </div>
</template>

<script>
// atoms
import { PromoCTA } from '@/components/atoms'

// molecules
import { FreeTrialForm } from '@/components/molecules'

export default {
    components: {
        PromoCTA,
        FreeTrialForm,
    },
}
</script>

<style lang="scss" scoped>
.right-content {
    height: 100vh;
    width: 50%;
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
}

@media only screen and (max-width: $mobile) {
    .right-content {
        height: 100%;
        width: 100%;
        margin-bottom: 40px;
    }
}
</style>
