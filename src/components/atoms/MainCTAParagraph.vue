<template>
    <p class="main-cta-paragraph">
        {{ text }}
    </p>
</template>

<script>
export default {
    props: {
        text: String,
    },
}
</script>

<style lang="scss" scoped>
.main-cta-paragraph {
    line-height: 26px;
    width: 100%;
    color: #fff;
    font-size: 1rem;
}
</style>
