<template>
    <h1 class="main-cta-text">{{ text }}</h1>
</template>

<script>
export default {
    props: {
        text: String,
    },
}
</script>

<style lang="scss" scoped>
.main-cta-text {
    color: #fff;
}
</style>
